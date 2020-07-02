---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620691"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="4f826-101">Доступ к выделенным элементам DataGrid WPF из события UnloadingRow DataGrid может привести к исключению NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="4f826-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="4f826-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4f826-102">Details</span></span>

<span data-ttu-id="4f826-103">Из-за ошибки в .NET Framework 4.5 обработчики событий <xref:System.Windows.Controls.DataGrid>, которые выполняют удаление строки, могут привести к созданию исключения <xref:System.NullReferenceException?displayProperty=fullName> при попытке получить доступ к свойствам <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> или <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName><xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="4f826-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4f826-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="4f826-104">Suggestion</span></span>

<span data-ttu-id="4f826-105">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f826-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="4f826-106">name</span><span class="sxs-lookup"><span data-stu-id="4f826-106">Name</span></span>    | <span data-ttu-id="4f826-107">Значение</span><span class="sxs-lookup"><span data-stu-id="4f826-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4f826-108">Область</span><span class="sxs-lookup"><span data-stu-id="4f826-108">Scope</span></span>   |<span data-ttu-id="4f826-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="4f826-109">Minor</span></span>|
|<span data-ttu-id="4f826-110">Version</span><span class="sxs-lookup"><span data-stu-id="4f826-110">Version</span></span>|<span data-ttu-id="4f826-111">4.5</span><span class="sxs-lookup"><span data-stu-id="4f826-111">4.5</span></span>|
|<span data-ttu-id="4f826-112">Type</span><span class="sxs-lookup"><span data-stu-id="4f826-112">Type</span></span>|<span data-ttu-id="4f826-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4f826-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4f826-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4f826-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
