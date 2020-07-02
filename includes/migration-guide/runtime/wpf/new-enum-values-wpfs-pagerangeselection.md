---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620702"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="007ce-101">Новые значения перечисления в перечислении PageRangeSelection WPF</span><span class="sxs-lookup"><span data-stu-id="007ce-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="007ce-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="007ce-102">Details</span></span>

<span data-ttu-id="007ce-103">Было добавлено два новых члена (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> и <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) в перечисление <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="007ce-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="007ce-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="007ce-104">Suggestion</span></span>

<span data-ttu-id="007ce-105">В большинстве случаев эти изменения не влияют на код пользователя.</span><span class="sxs-lookup"><span data-stu-id="007ce-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="007ce-106">Однако следует изменить код, зависящий от конкретного числа элементов, существующих в вызовах <xref:System.Enum.GetNames(System.Type)> или <xref:System.Enum.GetValues(System.Type)> к типу <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="007ce-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="007ce-107">name</span><span class="sxs-lookup"><span data-stu-id="007ce-107">Name</span></span>    | <span data-ttu-id="007ce-108">Значение</span><span class="sxs-lookup"><span data-stu-id="007ce-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="007ce-109">Область</span><span class="sxs-lookup"><span data-stu-id="007ce-109">Scope</span></span>   |<span data-ttu-id="007ce-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="007ce-110">Edge</span></span>|
|<span data-ttu-id="007ce-111">Version</span><span class="sxs-lookup"><span data-stu-id="007ce-111">Version</span></span>|<span data-ttu-id="007ce-112">4.5</span><span class="sxs-lookup"><span data-stu-id="007ce-112">4.5</span></span>|
|<span data-ttu-id="007ce-113">Type</span><span class="sxs-lookup"><span data-stu-id="007ce-113">Type</span></span>|<span data-ttu-id="007ce-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="007ce-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="007ce-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="007ce-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
