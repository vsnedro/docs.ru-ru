---
ms.openlocfilehash: 004e2d1883b631e88ab5e164b1120c3b081b7041
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496477"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="b3c2b-101">ConcurrentQueue&lt;T&gt;.TryPeek может возвращать ошибочные значения NULL в выходном параметре</span><span class="sxs-lookup"><span data-stu-id="b3c2b-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="b3c2b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b3c2b-102">Details</span></span>

<span data-ttu-id="b3c2b-103">В некоторых сценариях с несколькими потоками <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).</span><span class="sxs-lookup"><span data-stu-id="b3c2b-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3c2b-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="b3c2b-104">Suggestion</span></span>

<span data-ttu-id="b3c2b-105">Эта проблема решена в EntityFramework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="b3c2b-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="b3c2b-106">Чтобы устранить проблему, выполните обновление до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="b3c2b-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="b3c2b-107">name</span><span class="sxs-lookup"><span data-stu-id="b3c2b-107">Name</span></span>    | <span data-ttu-id="b3c2b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="b3c2b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3c2b-109">Область</span><span class="sxs-lookup"><span data-stu-id="b3c2b-109">Scope</span></span>   |<span data-ttu-id="b3c2b-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="b3c2b-110">Major</span></span>|
|<span data-ttu-id="b3c2b-111">Version</span><span class="sxs-lookup"><span data-stu-id="b3c2b-111">Version</span></span>|<span data-ttu-id="b3c2b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b3c2b-112">4.5</span></span>|
|<span data-ttu-id="b3c2b-113">Type</span><span class="sxs-lookup"><span data-stu-id="b3c2b-113">Type</span></span>|<span data-ttu-id="b3c2b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b3c2b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b3c2b-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b3c2b-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.ConcurrentQueue`1.TryPeek(`0@)``

-->
