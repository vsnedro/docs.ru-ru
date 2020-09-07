---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497748"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="2c184-101">Новые значения перечисления в перечислении PageRangeSelection WPF</span><span class="sxs-lookup"><span data-stu-id="2c184-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="2c184-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2c184-102">Details</span></span>

<span data-ttu-id="2c184-103">Было добавлено два новых члена (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> и <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) в перечисление <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2c184-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2c184-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="2c184-104">Suggestion</span></span>

<span data-ttu-id="2c184-105">В большинстве случаев эти изменения не влияют на код пользователя.</span><span class="sxs-lookup"><span data-stu-id="2c184-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="2c184-106">Однако следует изменить код, зависящий от конкретного числа элементов, существующих в вызовах <xref:System.Enum.GetNames(System.Type)> или <xref:System.Enum.GetValues(System.Type)> к типу <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2c184-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="2c184-107">name</span><span class="sxs-lookup"><span data-stu-id="2c184-107">Name</span></span>    | <span data-ttu-id="2c184-108">Значение</span><span class="sxs-lookup"><span data-stu-id="2c184-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2c184-109">Область</span><span class="sxs-lookup"><span data-stu-id="2c184-109">Scope</span></span>   |<span data-ttu-id="2c184-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="2c184-110">Edge</span></span>|
|<span data-ttu-id="2c184-111">Version</span><span class="sxs-lookup"><span data-stu-id="2c184-111">Version</span></span>|<span data-ttu-id="2c184-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2c184-112">4.5</span></span>|
|<span data-ttu-id="2c184-113">Type</span><span class="sxs-lookup"><span data-stu-id="2c184-113">Type</span></span>|<span data-ttu-id="2c184-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2c184-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2c184-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2c184-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
