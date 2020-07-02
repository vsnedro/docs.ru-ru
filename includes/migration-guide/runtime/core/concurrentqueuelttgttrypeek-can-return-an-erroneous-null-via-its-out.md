---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622145"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="6a00e-101">ConcurrentQueue&lt;T&gt;.TryPeek может возвращать ошибочные значения NULL в выходном параметре</span><span class="sxs-lookup"><span data-stu-id="6a00e-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="6a00e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6a00e-102">Details</span></span>

<span data-ttu-id="6a00e-103">В некоторых сценариях с несколькими потоками <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).</span><span class="sxs-lookup"><span data-stu-id="6a00e-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6a00e-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="6a00e-104">Suggestion</span></span>

<span data-ttu-id="6a00e-105">Эта проблема решена в EntityFramework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="6a00e-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="6a00e-106">Чтобы устранить проблему, выполните обновление до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="6a00e-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="6a00e-107">name</span><span class="sxs-lookup"><span data-stu-id="6a00e-107">Name</span></span>    | <span data-ttu-id="6a00e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="6a00e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a00e-109">Область</span><span class="sxs-lookup"><span data-stu-id="6a00e-109">Scope</span></span>   |<span data-ttu-id="6a00e-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="6a00e-110">Major</span></span>|
|<span data-ttu-id="6a00e-111">Version</span><span class="sxs-lookup"><span data-stu-id="6a00e-111">Version</span></span>|<span data-ttu-id="6a00e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6a00e-112">4.5</span></span>|
|<span data-ttu-id="6a00e-113">Type</span><span class="sxs-lookup"><span data-stu-id="6a00e-113">Type</span></span>|<span data-ttu-id="6a00e-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6a00e-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a00e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6a00e-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
