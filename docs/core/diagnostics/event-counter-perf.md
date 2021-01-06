---
title: Измерение производительности с помощью EventCounters в .NET Core
description: В этом руководстве вы узнаете, как измерять производительность с помощью EventCounters.
ms.date: 08/07/2020
ms.topic: tutorial
ms.openlocfilehash: 2ed7f234b685dab91ab275105d26b474e3bd1a87
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700747"
---
# <a name="tutorial-measure-performance-using-eventcounters-in-net-core"></a>Учебник. Измерение производительности с помощью EventCounters в .NET Core

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.0 и более поздних версий

В этом руководстве вы узнаете, как можно использовать <xref:System.Diagnostics.Tracing.EventCounter> для измерения производительности с высокой частотой событий. Вы можете использовать [доступные счетчики](available-counters.md), опубликованные в разных официальных пакетах .NET Core или сторонними поставщиками, либо создать собственные метрики для мониторинга.

Изучив данный учебник, вы научитесь:

> [!div class="checklist"]
>
> - Реализовывать <xref:System.Diagnostics.Tracing.EventSource>.
> - Организовывать мониторинг счетчиков с помощью [dotnet-counters](dotnet-counters.md).

## <a name="prerequisites"></a>Предварительные требования

В этом учебнике используется:

- [Пакет SDK для .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core) или более поздней версии.
- [dotnet-counters](dotnet-counters.md) для мониторинга счетчиков событий.
- [Пример целевого приложения отладки](/samples/dotnet/samples/diagnostic-scenarios) для диагностики.

## <a name="get-the-source"></a>Получение исходного кода

Пример приложения будет использоваться в качестве основания для мониторинга. [Пример репозитория ASP.NET](/samples/dotnet/samples/diagnostic-scenarios) доступен в обозревателе примеров. Скачайте ZIP-файл, извлеките его содержимое и откройте его в избранной интегрированной среде разработки. Выполните сборку приложения и запустите его, чтобы убедиться, что оно работает правильно, а затем закройте приложение.

## <a name="implement-an-eventsource"></a>Реализация счетчика событий

Для событий, происходящих каждые несколько миллисекунд, необходимо, чтобы затраты на событие были низкими (меньше миллисекунд). В противном случае влияние на производительность будет значительным. Регистрация события означает, что вы собираетесь записать что-то на диск. Если диск недостаточно быстродействующий, события будут потеряны. Потребуется решение, отличное от регистрации самого события.

При работе с большим количеством событий знание меры для каждого события не имеет смысла. В большинстве случаев достаточно лишь некоторой статистики. Так что вы можете получить статистику внутри самого процесса, а затем написать событие один раз в течение определенного времени для передачи статистики. Именно это и делает <xref:System.Diagnostics.Tracing.EventCounter>.

Ниже приведен пример реализации <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>. Создайте новый файл с именем *MinimalEventCounterSource.cs* и используйте фрагмент кода в качестве источника:

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

Строка <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> — это <xref:System.Diagnostics.Tracing.EventSource> часть, которая не является частью <xref:System.Diagnostics.Tracing.EventCounter>. Она была написана для того, чтобы показать, что можно зарегистрировать сообщение вместе со счетчиком событий.

## <a name="add-an-action-filter"></a>Добавление фильтра действий

Пример исходного кода является проектом ASP.NET Core. Вы можете глобально добавить [фильтр действий](/aspnet/core/mvc/controllers/filters#action-filters), который будет регистрировать общее время запроса. Создайте новый файл с именем *LogRequestTimeFilterAttribute.cs* и используйте следующий код:

```csharp
using System.Diagnostics;
using Microsoft.AspNetCore.Http.Extensions;
using Microsoft.AspNetCore.Mvc.Filters;

namespace DiagnosticScenarios
{
    public class LogRequestTimeFilterAttribute : ActionFilterAttribute
    {
        readonly Stopwatch _stopwatch = new Stopwatch();

        public override void OnActionExecuting(ActionExecutingContext context) => _stopwatch.Start();

        public override void OnActionExecuted(ActionExecutedContext context)
        {
            _stopwatch.Stop();

            MinimalEventCounterSource.Log.Request(
                context.HttpContext.Request.GetDisplayUrl(), _stopwatch.ElapsedMilliseconds);
        }
    }
}
```

Фильтр действий запускает <xref:System.Diagnostics.Stopwatch> по мере начала запроса и останавливается после завершения, записывая затраченное время. Общее число миллисекунд регистрируется в отдельном экземпляре `MinimalEventCounterSource`. Чтобы применить этот фильтр, необходимо добавить его в коллекцию фильтров. В файле *Startup.cs* обновите метод `ConfigureServices`, чтобы включить этот фильтр.

```csharp
public void ConfigureServices(IServiceCollection services) =>
    services.AddControllers(options => options.Filters.Add<LogRequestTimeFilterAttribute>())
            .AddNewtonsoftJson();
```

## <a name="monitor-event-counter"></a>Мониторинг счетчика событий

Реализовав <xref:System.Diagnostics.Tracing.EventSource> и настраиваемый фильтр действий, создайте и запустите приложение.
Вы зарегистрировали метрику в <xref:System.Diagnostics.Tracing.EventCounter>, но пока вы не получите доступ к статистике из нее, пользы от нее никакой. Чтобы получить статистику, необходимо включить <xref:System.Diagnostics.Tracing.EventCounter>, создав таймер, который срабатывает с периодичностью, которая требуется для событий и нужна прослушивателю для записи событий. Для этого можно использовать [dotnet-counters](dotnet-counters.md).

Используйте команду [dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps), чтобы отобразить список процессов .NET, которые можно отслеживать.

```console
dotnet-counters ps
```

Используя идентификатор процесса из выходных данных команды `dotnet-counters ps`, можно начать мониторинг счетчика событий с помощью следующей команды `dotnet-counters monitor`:

```console
dotnet-counters monitor --process-id 2196 --counters Sample.EventCounter.Minimal,Microsoft.AspNetCore.Hosting[total-requests,requests-per-second],System.Runtime[cpu-usage]
```

Во время выполнения команды `dotnet-counters monitor` удерживайте нажатой клавишу <kbd>F5</kbd> в браузере, чтобы начать выдачу непрерывных запросов к конечной точке `https://localhost:5001/api/values`. Через несколько секунд нажмите клавишу <kbd>q</kbd>.

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[Microsoft.AspNetCore.Hosting]
    Request Rate / 1 sec                               9
    Total Requests                                   134
[System.Runtime]
    CPU Usage (%)                                     13
[Sample.EventCounter.Minimal]
    Request Processing Time (ms)                      34.5
```

Команда `dotnet-counters monitor` отлично подходит для активного мониторинга. Однако может потребоваться собрать эти метрики диагностики для обработки и анализа. Для этого используйте команду `dotnet-counters collect`. Команда `collect` аналогична команде `monitor`, но принимает несколько дополнительных параметров. Можно указать требуемое имя выходного файла и формат. Для файла JSON с именем *diagnostics.json* используйте следующую команду:

```console
dotnet-counters collect --process-id 2196 --format json -o diagnostics.json --counters Sample.EventCounter.Minimal,Microsoft.AspNetCore.Hosting[total-requests,requests-per-second],System.Runtime[cpu-usage]
```

Во время выполнения команды удерживайте нажатой клавишу <kbd>F5</kbd> в браузере, чтобы начать выдачу непрерывных запросов к конечной точке `https://localhost:5001/api/values`. Через несколько секунд нажмите клавишу <kbd>q</kbd>. Файл *diagnostics.json* будет записан. Однако файл JSON не имеет отступа; для удобства чтения здесь он отображается с отступом.

```json
{
  "TargetProcess": "DiagnosticScenarios",
  "StartTime": "8/5/2020 3:02:45 PM",
  "Events": [
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    }
  ]
}
```

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Счетчики событий](event-counters.md)
