---
title: Регистрация с Azure SDK для .NET
description: Узнайте, как включить журнал с помощью SDK Azure для библиотек клиентов .NET
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433226"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>Регистрация с Azure SDK для .NET

[SDK Azure](https://azure.microsoft.com/downloads/) для клиентских библиотек .NET включает в себя возможность регистрации операций библиотеки клиентов. Это позволяет отслеживать запросы на ввог/ои и ответы, которые библиотеки клиентов делают для служб Azure. Как правило, журналы используются для отладки или диагностики проблем связи. В этой статье описаны три подхода, позволяющие вести журнал с Azure SDK для .NET:

- Вход в окно консоли
- Следы диагностики входа в .NET
- Настройка пользовательских журналов

> [!IMPORTANT]
> Эта статья распространяется на клиентские библиотеки, в которых используются самые последние версии SDK Azure для .NET. Чтобы узнать, поддерживается ли библиотека, обратитесь к списку [последних релизов Azure SDK.](https://azure.github.io/azure-sdk/releases/latest/index.html) Если приложение использует старую версию библиотек клиентов Azure SDK, обратитесь к конкретным инструкциям в соответствующей документации службы.

## <a name="log-information"></a>Сведения о журнале

SDK регистрирует следующую информацию, дезинфицируя параметры запроса и значения заголовка для удаления личных данных.

Запись журнала запроса HTTP:

- Уникальный ИД
- Метод HTTP
- URI
- Исходящие заголовки запросов

Запись журнала ответов HTTP:

- Продолжительность операции ввоза/о (время истечения)
- Request ID (ИД запроса)
- HTTP status code (Код состояния HTTP)
- Фраза причины HTTP
- Заголовки ответов
- Информация об ошибке, когда это применимо

Для содержания запроса и ответа:

- Поток содержимого как текст или байты в зависимости от заголовка Content-Type.
     > [! ПРИМЕЧАНИЕ- Запись контента отключена по умолчанию. Для включения, `Diagnostics.IsLoggingContentEnabled` `true` установить `ClientOptions`в .

Регистры событий выходят обычно на одном из этих трех уровней:

- Информационные для событий запроса и ответа
- Предупреждение об ошибках
- Verbose для подробных сообщений и регистрации контента

## <a name="enable-logging-with-built-in-methods"></a>Включить вход с помощью встроенных методов

Azure SDK для библиотек клиентов .NET регистрирует события в отслеживании событий для Windows (ETW) через [ `EventSource` класс,](/dotnet/api/system.diagnostics.tracing.eventsource)что характерно для .NET. Источники событий позволяют использовать структурированную систему в коде приложения с минимальными накладными затратами на производительность. Чтобы получить доступ к этим журналам событий, необходимо зарегистрировать слушателей событий.

SDK включает `Azure.Core.Diagnostics.AzureEventSourceListener` в себя класс (определенный в пакете Azure.Core NuGet), который содержит два `CreateConsoleLogger` `CreateTraceLogger`статических метода, которые упрощают всеобъемлющий журнал для вашего приложения .NET: и . Эти методы принимают дополнительный параметр, который определяет уровень журнала.

### <a name="log-to-the-console-window"></a>Вход в окно консоли

Основным принципом SDK Azure для клиентских библиотек .NET является упрощение возможности просмотра всеобъемлющих журналов в режиме реального времени. Метод `CreateConsoleLogger` позволяет отправлять журналы в окно консоли с одной строкой кода:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Вход в диагностические следы

При реализации отслеживания трассировки можно использовать `CreateTraceLogger` метод для входа в[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)стандартный механизм отслеживания событий .NET (). Для получения дополнительной информации о отслеживании событий в .NET, [см.](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners) Этот пример определяет уровень многословного регистра:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Настройка пользовательских журналов

Как уже упоминалось выше, необходимо зарегистрировать слушателей событий для получения сообщений журнала от Azure SDK для .NET. Если вы не хотите осуществлять всеобъемлющую систему регистрации, используя один из `AzureEventSourceListener` приведенных выше упрощенных методов, можно построить экземпляр класса и передать ему функцию обратного вызова, которую вы пишете. Этот метод будет получать сообщения журнала, которые вы можете обработать, как вам нужно. Кроме того, при построении экземпляра можно указать уровни журнала для включения.

Следующий пример создает слушателя событий, который регистрируется на консоли с пользовательским сообщением и фильтруется в основные события Azure многословного уровня.

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a>Следующие шаги

- [Включить журнал диагностики для приложений в службе приложений Azure](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- Просмотрите параметры [регистрации и аудита безопасности Azure](https://docs.microsoft.com/azure/security/fundamentals/log-audit)
- Узнайте, как работать с [журналами платформы Azure](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)
- Подробнее о [журнале и отслеживании ядра .NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)
