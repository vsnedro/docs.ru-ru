---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614777"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase не распространяет исключения OnStart

#### <a name="details"></a>Подробнее

В .NET Framework 4.7 и более ранних версий исключения, возникшие при запуске службы, не распространяются на вызывающий объект <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.<br/>Начиная с приложений, предназначенных для .NET Framework 4.7.1, среда выполнения распространяет исключения в <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> для служб, которые не удается запустить.

#### <a name="suggestion"></a>Предложение

Если при запуске службы есть исключение, оно будет распространяться. Это поможет диагностировать случаи сбоя запуска служб. <br/>Если такое поведение нежелательно, от него можно отказаться, добавив следующий элемент &lt;AppContextSwitchOverrides&gt; в раздел &lt;runtime&gt; файла конфигурации приложения:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

Если приложение предназначено для версии до 4.7.1, но вы хотите использовать это поведение, добавьте следующий элемент &lt;AppContextSwitchOverrides&gt; в раздел &lt;runtime&gt; файла конфигурации приложения:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Версия | 4.7.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
