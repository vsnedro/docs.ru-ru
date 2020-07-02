---
ms.openlocfilehash: fc6066fd0b23d299158114cb397934041b99ba47
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620703"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="2fc7d-101">Метод DispatcherSynchronizationContext.CreateCopy WPF теперь возвращает новую копию вместо текущего экземпляра</span><span class="sxs-lookup"><span data-stu-id="2fc7d-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="2fc7d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2fc7d-102">Details</span></span>

<span data-ttu-id="2fc7d-103">В .NET Framework 4 метод <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> возвращал ссылку на текущий экземпляр главным образом в качестве оптимизации производительности.</span><span class="sxs-lookup"><span data-stu-id="2fc7d-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="2fc7d-104">В .NET Framework 4.5 он возвращает новый экземпляр, что позволяет впервые делать заключение о том, что одинаковые ссылки указывают на то, что выполняющийся поток находится в правильном контексте синхронизации.</span><span class="sxs-lookup"><span data-stu-id="2fc7d-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="2fc7d-105">Маловероятно, что будет затронут код, который проверяет подлинность этих ссылок, но в связи с изменением необходимо протестировать код, который вызывает <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy>, в ходе миграции на .NET Framework 4.5 или более позднюю версию.</span><span class="sxs-lookup"><span data-stu-id="2fc7d-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2fc7d-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="2fc7d-106">Suggestion</span></span>

<span data-ttu-id="2fc7d-107">Учитывайте, что <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> теперь возвращает новый объект <xref:System.Threading.SynchronizationContext?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2fc7d-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="2fc7d-108">Ранее код, который использовал эквивалентность ссылок, на самом деле не проверялся на нахождение в правильном контексте, но проверяется при создании в .NET Framework 4.5 или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="2fc7d-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="2fc7d-109">Хотя маловероятно, что это приведет к серьезным проблемам, проверки путей к затронутому коду должно быть достаточно для определения проблемы.</span><span class="sxs-lookup"><span data-stu-id="2fc7d-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="2fc7d-110">name</span><span class="sxs-lookup"><span data-stu-id="2fc7d-110">Name</span></span>    | <span data-ttu-id="2fc7d-111">Значение</span><span class="sxs-lookup"><span data-stu-id="2fc7d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2fc7d-112">Область</span><span class="sxs-lookup"><span data-stu-id="2fc7d-112">Scope</span></span>   |<span data-ttu-id="2fc7d-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="2fc7d-113">Minor</span></span>|
|<span data-ttu-id="2fc7d-114">Version</span><span class="sxs-lookup"><span data-stu-id="2fc7d-114">Version</span></span>|<span data-ttu-id="2fc7d-115">4.5</span><span class="sxs-lookup"><span data-stu-id="2fc7d-115">4.5</span></span>|
|<span data-ttu-id="2fc7d-116">Type</span><span class="sxs-lookup"><span data-stu-id="2fc7d-116">Type</span></span>|<span data-ttu-id="2fc7d-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2fc7d-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2fc7d-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2fc7d-118">Affected APIs</span></span>

-<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
