---
ms.openlocfilehash: bca76daca6e9c424377a80aa56e1a5ff191be5ca
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497548"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="d0df6-101">Периодически не удается выполнить прокрутку до нижнего элемента в ItemsControls (таких как ListBox и DataGrid) при использовании пользовательских DataTemplates</span><span class="sxs-lookup"><span data-stu-id="d0df6-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="d0df6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d0df6-102">Details</span></span>

<span data-ttu-id="d0df6-103">В некоторых случаях ошибка в .NET Framework 4.5 приводит к тому, что ItemsControls (например, <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> и т. д.) не удается выполнить прокрутку до нижнего элемента при использовании пользовательских DataTemplates.</span><span class="sxs-lookup"><span data-stu-id="d0df6-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="d0df6-104">Если попытка прокрутки предпринимается повторно (после прокрутки вверх), прокрутка будет работать.</span><span class="sxs-lookup"><span data-stu-id="d0df6-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d0df6-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="d0df6-105">Suggestion</span></span>

<span data-ttu-id="d0df6-106">Эта проблема была устранена в .NET Framework 4.5.2 и может быть решена путем обновления до этой версии (или более поздней) платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0df6-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="d0df6-107">Кроме того, пользователи по-прежнему могут перетаскивать полосы прокрутки к последним элементам в этих коллекциях, однако для успешного выполнения этой задачи это может потребоваться сделать дважды.</span><span class="sxs-lookup"><span data-stu-id="d0df6-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="d0df6-108">name</span><span class="sxs-lookup"><span data-stu-id="d0df6-108">Name</span></span>    | <span data-ttu-id="d0df6-109">Значение</span><span class="sxs-lookup"><span data-stu-id="d0df6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d0df6-110">Область</span><span class="sxs-lookup"><span data-stu-id="d0df6-110">Scope</span></span>   |<span data-ttu-id="d0df6-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="d0df6-111">Minor</span></span>|
|<span data-ttu-id="d0df6-112">Version</span><span class="sxs-lookup"><span data-stu-id="d0df6-112">Version</span></span>|<span data-ttu-id="d0df6-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d0df6-113">4.5</span></span>|
|<span data-ttu-id="d0df6-114">Type</span><span class="sxs-lookup"><span data-stu-id="d0df6-114">Type</span></span>|<span data-ttu-id="d0df6-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d0df6-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d0df6-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d0df6-116">Affected APIs</span></span>

<span data-ttu-id="d0df6-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="d0df6-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
