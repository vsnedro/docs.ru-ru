---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496294"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="0aad1-101">Проблема с привязкой ListBoxItem IsSelected к ObservableCollection&lt;T&gt;.Move</span><span class="sxs-lookup"><span data-stu-id="0aad1-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="0aad1-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0aad1-102">Details</span></span>

<span data-ttu-id="0aad1-103">Вызов <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> или <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> для коллекции, привязанной к <xref:System.Windows.Controls.ListBox?displayProperty=fullName> с выделенными элементами, может привести к последующему выделению или отмене выделения элементов <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="0aad1-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0aad1-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="0aad1-104">Suggestion</span></span>

<span data-ttu-id="0aad1-105">Чтобы обойти эту проблему, выполните вызов <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> и <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> вместо <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)>.</span><span class="sxs-lookup"><span data-stu-id="0aad1-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="0aad1-106">Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0aad1-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="0aad1-107">name</span><span class="sxs-lookup"><span data-stu-id="0aad1-107">Name</span></span>    | <span data-ttu-id="0aad1-108">Значение</span><span class="sxs-lookup"><span data-stu-id="0aad1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0aad1-109">Область</span><span class="sxs-lookup"><span data-stu-id="0aad1-109">Scope</span></span>   |<span data-ttu-id="0aad1-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="0aad1-110">Minor</span></span>|
|<span data-ttu-id="0aad1-111">Version</span><span class="sxs-lookup"><span data-stu-id="0aad1-111">Version</span></span>|<span data-ttu-id="0aad1-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0aad1-112">4.5</span></span>|
|<span data-ttu-id="0aad1-113">Type</span><span class="sxs-lookup"><span data-stu-id="0aad1-113">Type</span></span>|<span data-ttu-id="0aad1-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0aad1-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0aad1-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0aad1-115">Affected APIs</span></span>

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
