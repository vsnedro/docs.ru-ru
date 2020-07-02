---
ms.openlocfilehash: f4ff938b2d0e9ead481fdf239aed8a6b918a99b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620697"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="e4dd9-101">Проблема с привязкой ListBoxItem IsSelected к ObservableCollection&lt;T&gt;.Move</span><span class="sxs-lookup"><span data-stu-id="e4dd9-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="e4dd9-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e4dd9-102">Details</span></span>

<span data-ttu-id="e4dd9-103">Вызов <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> или <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> для коллекции, привязанной к <xref:System.Windows.Controls.ListBox?displayProperty=fullName> с выделенными элементами, может привести к последующему выделению или отмене выделения элементов <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e4dd9-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="e4dd9-104">Suggestion</span></span>

<span data-ttu-id="e4dd9-105">Чтобы обойти эту проблему, выполните вызов <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> и <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> вместо <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)>.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="e4dd9-106">Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="e4dd9-107">name</span><span class="sxs-lookup"><span data-stu-id="e4dd9-107">Name</span></span>    | <span data-ttu-id="e4dd9-108">Значение</span><span class="sxs-lookup"><span data-stu-id="e4dd9-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e4dd9-109">Область</span><span class="sxs-lookup"><span data-stu-id="e4dd9-109">Scope</span></span>   |<span data-ttu-id="e4dd9-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e4dd9-110">Minor</span></span>|
|<span data-ttu-id="e4dd9-111">Version</span><span class="sxs-lookup"><span data-stu-id="e4dd9-111">Version</span></span>|<span data-ttu-id="e4dd9-112">4.5</span><span class="sxs-lookup"><span data-stu-id="e4dd9-112">4.5</span></span>|
|<span data-ttu-id="e4dd9-113">Type</span><span class="sxs-lookup"><span data-stu-id="e4dd9-113">Type</span></span>|<span data-ttu-id="e4dd9-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e4dd9-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e4dd9-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e4dd9-115">Affected APIs</span></span>

-<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
