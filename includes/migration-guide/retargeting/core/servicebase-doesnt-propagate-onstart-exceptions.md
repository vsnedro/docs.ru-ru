---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614777"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="06f67-101">ServiceBase не распространяет исключения OnStart</span><span class="sxs-lookup"><span data-stu-id="06f67-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="06f67-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="06f67-102">Details</span></span>

<span data-ttu-id="06f67-103">В .NET Framework 4.7 и более ранних версий исключения, возникшие при запуске службы, не распространяются на вызывающий объект <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06f67-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span></span><br/><span data-ttu-id="06f67-104">Начиная с приложений, предназначенных для .NET Framework 4.7.1, среда выполнения распространяет исключения в <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> для служб, которые не удается запустить.</span><span class="sxs-lookup"><span data-stu-id="06f67-104">Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="06f67-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="06f67-105">Suggestion</span></span>

<span data-ttu-id="06f67-106">Если при запуске службы есть исключение, оно будет распространяться.</span><span class="sxs-lookup"><span data-stu-id="06f67-106">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="06f67-107">Это поможет диагностировать случаи сбоя запуска служб.</span><span class="sxs-lookup"><span data-stu-id="06f67-107">This should help diagnose cases where services fail to start.</span></span> <br/><span data-ttu-id="06f67-108">Если такое поведение нежелательно, от него можно отказаться, добавив следующий элемент &lt;AppContextSwitchOverrides&gt; в раздел &lt;runtime&gt; файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="06f67-108">If this behavior is undesirable, you can opt out of it by adding the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

<span data-ttu-id="06f67-109">Если приложение предназначено для версии до 4.7.1, но вы хотите использовать это поведение, добавьте следующий элемент &lt;AppContextSwitchOverrides&gt; в раздел &lt;runtime&gt; файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="06f67-109">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| <span data-ttu-id="06f67-110">name</span><span class="sxs-lookup"><span data-stu-id="06f67-110">Name</span></span>    | <span data-ttu-id="06f67-111">Значение</span><span class="sxs-lookup"><span data-stu-id="06f67-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="06f67-112">Область</span><span class="sxs-lookup"><span data-stu-id="06f67-112">Scope</span></span>   | <span data-ttu-id="06f67-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="06f67-113">Minor</span></span>       |
| <span data-ttu-id="06f67-114">Версия</span><span class="sxs-lookup"><span data-stu-id="06f67-114">Version</span></span> | <span data-ttu-id="06f67-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="06f67-115">4.7.1</span></span>       |
| <span data-ttu-id="06f67-116">Type</span><span class="sxs-lookup"><span data-stu-id="06f67-116">Type</span></span>    | <span data-ttu-id="06f67-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="06f67-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="06f67-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="06f67-118">Affected APIs</span></span>

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
