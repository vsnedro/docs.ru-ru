---
title: Распределенная трассировка — .NET
description: Общие сведения о распределенной трассировке .NET.
ms.date: 02/02/2021
ms.openlocfilehash: d29c803dfec00474562abdc61ce65ea3f3faa133
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431442"
---
# <a name="net-distributed-tracing"></a>Распределенная трассировка .NET

Распределенная трассировка — это способ публикации и наблюдения за данными трассировки в распределенной системе.
.NET Framework и .NET Core поддерживают трассировку с использованием API <xref:System.Diagnostics>.

- Класс <xref:System.Diagnostics.Activity?displayProperty=nameWithType> позволяет хранить и получать доступ к контексту диагностики и использовать его в системе ведения журналов.
- Класс <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType> позволяет инструментировать код для ведения журнала расширенных полезных данных во время производства, которые будут использоваться в инструментированном процессе.

Ниже приведен пример публикации данных трассировки из входящих запросов HTTP:

```csharp
   public void OnIncomingRequest(DiagnosticListener httpListener, HttpContext context)
   {
       if (httpListener.IsEnabled("Http_In"))
       {
           var activity = new Activity("Http_In");

           //add tags, baggage, etc.
           activity.SetParentId(context.Request.headers["Request-id"])
           foreach (var pair in context.Request.Headers["Correlation-Context"])
           {
               var baggageItem = NameValueHeaderValue.Parse(pair);
               activity.AddBaggage(baggageItem.Key, baggageItem.Value);
           }
           httpListener.StartActivity(activity, new { context });
           try
           {
               //process request ...
           }
           finally
           {
               //stop activity
               httpListener.StopActivity(activity, new {context} );
           }
       }
   }
```

Ниже приведен пример прослушивания событий Activity:

```csharp
    DiagnosticListener.AllListeners.Subscribe(delegate (DiagnosticListener listener)
    {
        if (listener.Name == "MyActivitySource")
        {
            listener.Subscribe(delegate (KeyValuePair<string, object> value)
            {
                if (value.Key.EndsWith("Start", StringComparison.Ordinal))
                    LogActivityStart();
                else if (value.Key.EndsWith("Stop", StringComparison.Ordinal))
                    LogActivityStop();
            });
        }
    }
```

В .NET 5.0 расширены возможности распределенной трассировки, чтобы разрешить сценарии [OpenTelemetry](https://opentelemetry.io/), добавленные возможности выборки и упрощенный шаблон кода трассировки, а также упростить и сделать более удобным прослушивание событий Activity.

> [!NOTE]
> Для получения доступа ко всем добавленным возможностям .NET 5.0 убедитесь, что проект ссылается на класс [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/) пакета NuGet версии 5.0 или более поздней. Этот пакет можно использовать в библиотеках и приложениях, предназначенных для любой поддерживаемой версии .NET Framework, .NET Core и .NET Standard. При использовании .NET версии 5.0 или более поздней нет необходимости создавать ссылку на пакет вручную, так как он включен в общую библиотеку, установленную вместе со средой выполнения .NET.

## <a name="getting-started-with-tracing"></a>Начало работы с трассировкой

Приложения и библиотеки могут легко публиковать данные трассировки, просто используя классы <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> и <xref:System.Diagnostics.Activity?displayProperty=nameWithType>.

### <a name="activitysource"></a>ActivitySource

Первый шаг при публикации данных трассировки — создание экземпляра класса ActivitySource. ActivitySource — это класс, предоставляющий API для создания и запуска объектов Activity, а также для регистрации объектов ActivityListener для прослушивания событий Activity.

```csharp
    private static ActivitySource source = new ActivitySource("MyCompany.MyComponent.SourceName", "v1");
```

#### <a name="best-practices"></a>Рекомендации

- Создайте класс ActivitySource и сохраните его в статической переменной, а затем используйте этот экземпляр при необходимости.

- Имя источника, передаваемое конструктору, должно быть уникальным, чтобы избежать конфликтов с другими источниками. Рекомендуется использовать иерархическое имя, содержащее название компании, имя компонента и имя источника. Например, `Microsoft.System.HttpClient.HttpInOutRequests`.

- Параметр version является необязательным. Рекомендуется указывать версию, если планируется выпуск нескольких версий библиотеки или приложения и вам нужно различать источники разных версий.

### <a name="activity-creation"></a>Создание объектов Activity

Теперь созданный объект ActivitySource можно использовать для создания и запуска объектов Activity, которые используются для записи данных трассировки в нужных местах в коде.

```csharp
        using (Activity activity = source.StartActivity("OperationName"))
        {
            // Do something

            activity?.AddTag("key", "value"); // log the tracing
        }
```

В этом примере кода создается объект Activity, а затем записываются некоторые теги трассировки `key` и `value`.

#### <a name="notes"></a>Примечания

- `ActivitySource.StartActivity` пытается создать и запустить действие в то же время. В приведенном шаблоне кода используется блок `using`, который автоматически удаляет созданный объект Activity после выполнения блока. Удаление объекта Activity прервет это запущенное действие, и коду не нужно будет явно останавливать его. Это упрощает шаблон кода.

- `ActivitySource.StartActivity` внутренним образом определяет наличие прослушивателей для таких событий. Если зарегистрированных прослушивателей нет или есть прослушиватели, которые не заинтересованы в таком событии, `ActivitySource.StartActivity` просто вернет `null`, не создавая объект Activity. Именно поэтому в коде использовался допускающий значение NULL оператор `?` в инструкции `activity?.AddTag`. Как правило, внутри блока `using` всегда следует использовать допускающий значение NULL оператор `?` после имени объекта действия.

## <a name="listening-to-the-activity-events"></a>Прослушивание событий Activity

.NET предоставляет класс <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType>, который можно использовать для прослушивания событий Activity, активируемых из одного или нескольких экземпляров ActivitySource.
Прослушиватель можно использовать для получения данных трассировки, выборки или принудительного создания объекта Activity.

Класс `ActivityListener` предоставляет разные обратные вызовы для управления разными событиями.

```csharp

ActivityListener listener = new ActivityListener()

ShouldListenTo = (activitySource) => object.ReferenceEquals(source, activitySource),
ActivityStarted = activity => /* Handle the Activity start event here */ DoSomething(),
ActivityStopped = activity => /* Handle the Activity stop event here */ DoSomething(),
SampleUsingParentId = (ref ActivityCreationOptions<string> activityOptions) => ActivitySamplingResult.AllData,
Sample = (ref ActivityCreationOptions<ActivityContext> activityOptions) => ActivitySamplingResult.AllData

// Enable the listener
ActivitySource.AddActivityListener(listener);
```

- `ShouldListenTo` включает прослушивание определенных объектов `ActivitySource`. В этом примере разрешается прослушивание ранее созданного объекта `ActivitySource`. Для прослушивания любых других объектов `ActivitySource` можно обеспечить большую гибкость, проверив `Name` и `Version` входного экземпляра `ActivitySource`.

- `ActivityStarted` и `ActivityStopped` позволяют получать события Start и Stop `Activity` для всех объектов `Activity`, созданных объектами `ActivitySource`, которые были включены при обратном вызове `ShouldListenTo`.

- `Sample` и `SampleUsingParentId` являются основными методами обратного вызова, предназначенными для выборки. Эти два обратных вызова возвращают значение перечисления `ActivitySamplingResult`, которое может указывать на выборку из текущего запроса на создание `Activity`. Если обратный вызов возвращает `ActivitySamplingResult.None` и другие включенные прослушиватели не возвращают другое значение, объект Activity не будет создан и `ActivitySource.StartActivity` вернет `null`. В противном случае будет создан объект `Activity`.

## <a name="net-50-new-features"></a>Новые возможности .NET 5.0

Некоторое время класс `Activity` поддерживал сценарии трассировки. Он позволял добавлять теги, которые представляют собой пары "ключ-значение" данных трассировки. Также класс поддерживал Baggage, то есть пары "ключ-значение", предназначенные для распространения по сети.

.NET 5.0 поддерживает дополнительные функции, в основном для включения сценариев OpenTelemetry.

### <a name="activitycontext"></a>ActivityContext

<xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType> — это структура, которая содержит контекст операций трассировки (включая идентификатор трассировки, идентификатор диапазона, флаги трассировки и состояние трассировки). Теперь можно создать новый объект `Activity`, предоставляющий родительский контекст трассировки. Кроме того, можно легко извлечь контекст трассировки из любого объекта `Activity`, вызвав свойство `Activity.Context`.

### <a name="activitylink"></a>ActivityLink

<xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType> — это структура, содержащая экземпляр контекста трассировки, который может быть связан со случайным образом связанными объектами `Activity`. Ссылки можно добавить в объект `Activity`, передав список ссылок в метод `ActivitySource.StartActivity` при создании `Activity`. Связанные с объектом `Activity` ссылки можно получить с помощью свойства `Activity.Links`.

### <a name="activityevent"></a>ActivityEvent

<xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType> представляет событие, которое содержит имя и метку времени, а также необязательный список тегов. События можно добавить в объект `Activity`, вызвав метод `Activity.AddEvent`. Весь список событий объекта `Activity` можно получить с помощью свойства `Activity.Events`.

### <a name="activitykind"></a>ActivityKind

<xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType> описывает связь между действием, а также его родительскими и дочерними элементами в трассировке. Для типа можно задать объект `Activity`, передав значение типа в метод `ActivitySource.StartActivity` при создании `Activity`. Тип объекта `Activity` можно получить с помощью свойства `Activity.Kind`.

### <a name="isalldatarequested"></a>IsAllDataRequested

<xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType> указывает, должно ли это действие быть заполнено всеми сведениями о распространении, а также всеми другими свойствами, такими как ссылки, теги и события. Значение `IsAllDataRequested` определяется из результата, полученного из всех прослушивателей обратных вызовов `Sample` и `SampleUsingParentId`. Значение можно получить с помощью свойства `Activity.IsAllDataRequested`.

### <a name="activitysource"></a>Activity.Source

<xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType> получает источник действия, связанный с этим действием.

### <a name="activitydisplayname"></a>Activity.DisplayName

<xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType> позволяет получить или задать отображаемое имя для действия.

### <a name="activitytagobjects"></a>Activity.TagObjects

Класс `Activity` имеет свойство `Activity.Tags`, которое возвращает список пар "ключ-значение" для ключа и значения строкового типа. Такие теги можно добавить в `Activity` с помощью метода `AddTag(string, string)`. `Activity` расширяет поддержку тегов, предоставляя перегруженный метод `AddTag(string, object)`, который допускает значения любого типа.  Полный список таких тегов можно получить с помощью <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>.

## <a name="sampling"></a>Выборка

Выборка — это механизм управления шумом и издержками путем снижения числа выборок трассировок, собираемых и отправляемых в серверную часть. Выборка — это важный сценарий OpenTelemetry. В .NET 5.0 можно легко разрешить выборку. Рекомендуется создать новые объекты `Activity` с помощью `ActivitySource.StartActivity` и попытаться предоставить все возможные доступные данные (включая теги, типы, ссылки и т. д.) при вызове этого метода. Предоставление данных позволит средствам выборки, реализованным с помощью `ActivityListener`, иметь правильное решение для выборки. Если важна производительность, чтобы избежать создания данных перед созданием объекта `Activity`, можно использовать свойство `ActivitySource.HasListeners` для определения того, есть ли прослушиватели.

## <a name="opentelemetry"></a>OpenTelemetry

В состав пакета SDK OpenTelemetry входят многие функции с поддержкой комплексных сценариев распределенной трассировки. Он предоставляет несколько средств выборки и средств экспорта, которые можно выбрать. Он также позволяет создавать пользовательские средства выборки и средства экспорта.

OpenTelemetry поддерживает экспорт собранных данных трассировки в разные серверные части (включая Jaeger, Zipkin, New Relic и т. д.). Дополнительные сведения см. в описании [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/). Также на сайте Nuget.org можно найти пакеты, начинающиеся с `OpenTelemetry.Exporter.`, чтобы получить список пакетов средств экспорта.

Ниже приведен пример кода, перенесенного из [руководства по началу работы с OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started). Вы можете увидеть, насколько легко выполнить выборку и экспорт данных трассировки в консоль.

```csharp
// <copyright file="Program.cs" company="OpenTelemetry Authors">
// Copyright The OpenTelemetry Authors
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//     http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.
// </copyright>

using System.Diagnostics;
using OpenTelemetry;
using OpenTelemetry.Trace;

public class Program
{
    private static readonly ActivitySource MyActivitySource = new ActivitySource(
        "MyCompany.MyProduct.MyLibrary");

    public static void Main()
    {
        using var tracerProvider = Sdk.CreateTracerProviderBuilder()
            .SetSampler(new AlwaysOnSampler())
            .AddSource("MyCompany.MyProduct.MyLibrary")
            .AddConsoleExporter()
            .Build();

        using (var activity = MyActivitySource.StartActivity("SayHello"))
        {
            activity?.SetTag("foo", 1);
            activity?.SetTag("bar", "Hello, World!");
            activity?.SetTag("baz", new int[] { 1, 2, 3 });
        }
    }
}
```

Выборка должна ссылаться на пакет [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2).
