---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614645"
---
### <a name="throttle-concurrent-requests-per-session"></a><span data-ttu-id="0bd87-101">Регулирование одновременных запросов за сеанс</span><span class="sxs-lookup"><span data-stu-id="0bd87-101">Throttle concurrent requests per session</span></span>

#### <a name="details"></a><span data-ttu-id="0bd87-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0bd87-102">Details</span></span>

<span data-ttu-id="0bd87-103">В платформе .NET Framework 4.6.2 и более ранних версий ASP.NET выполняет запросы с тем же идентификатором Sessionid последовательно, а ASP.NET всегда выдает Sessionid через файл cookie по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0bd87-103">In the .NET Framework 4.6.2 and earlier, ASP.NET executes requests with the same Sessionid sequentially, and ASP.NET always issues the Sessionid through cookies by default.</span></span> <span data-ttu-id="0bd87-104">Если страница отвечает слишком медленно, при нажатии клавиши <kbd>F5</kbd> в браузере производительность сервера значительно снизится.</span><span class="sxs-lookup"><span data-stu-id="0bd87-104">If a page takes a long time to respond, it will significantly degrade server performance just by pressing <kbd>F5</kbd> on the browser.</span></span> <span data-ttu-id="0bd87-105">В исправлении добавлен счетчик, который отслеживает запросы в очереди и завершает запросы, если они превышают заданное ограничение.</span><span class="sxs-lookup"><span data-stu-id="0bd87-105">In the fix, we added a counter to track the queued requests and terminate the requests when they exceed a specified limit.</span></span> <span data-ttu-id="0bd87-106">Значение по умолчанию — 50.</span><span class="sxs-lookup"><span data-stu-id="0bd87-106">The default value is 50.</span></span> <span data-ttu-id="0bd87-107">Если ограничение достигнуто, в журнал событий записывается предупреждение, а в журнале IIS может быть записан ответ HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="0bd87-107">If the limit is reached, a warning will be logged in the event log, and an HTTP 500 response may be recorded in the IIS log.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0bd87-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="0bd87-108">Suggestion</span></span>

<span data-ttu-id="0bd87-109">Чтобы восстановить прежнее поведение, можно добавить следующий параметр в файл web.config для отказа от нового поведения.</span><span class="sxs-lookup"><span data-stu-id="0bd87-109">To restore the old behavior, you can add the following setting to your web.config file to opt out of the new behavior.</span></span>

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| <span data-ttu-id="0bd87-110">name</span><span class="sxs-lookup"><span data-stu-id="0bd87-110">Name</span></span>    | <span data-ttu-id="0bd87-111">Значение</span><span class="sxs-lookup"><span data-stu-id="0bd87-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0bd87-112">Область</span><span class="sxs-lookup"><span data-stu-id="0bd87-112">Scope</span></span>   | <span data-ttu-id="0bd87-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0bd87-113">Edge</span></span>        |
| <span data-ttu-id="0bd87-114">Version</span><span class="sxs-lookup"><span data-stu-id="0bd87-114">Version</span></span> | <span data-ttu-id="0bd87-115">4.7</span><span class="sxs-lookup"><span data-stu-id="0bd87-115">4.7</span></span>         |
| <span data-ttu-id="0bd87-116">Type</span><span class="sxs-lookup"><span data-stu-id="0bd87-116">Type</span></span>    | <span data-ttu-id="0bd87-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="0bd87-117">Retargeting</span></span> |
