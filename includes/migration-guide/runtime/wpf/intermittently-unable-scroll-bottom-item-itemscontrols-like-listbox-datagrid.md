---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622120"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="f4942-101">Периодически не удается выполнить прокрутку до нижнего элемента в ItemsControls (таких как ListBox и DataGrid) при использовании пользовательских DataTemplates</span><span class="sxs-lookup"><span data-stu-id="f4942-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="f4942-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f4942-102">Details</span></span>

<span data-ttu-id="f4942-103">В некоторых случаях ошибка в .NET Framework 4.5 приводит к тому, что ItemsControls (например, <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> и т. д.) не удается выполнить прокрутку до нижнего элемента при использовании пользовательских DataTemplates.</span><span class="sxs-lookup"><span data-stu-id="f4942-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="f4942-104">Если попытка прокрутки предпринимается повторно (после прокрутки вверх), прокрутка будет работать.</span><span class="sxs-lookup"><span data-stu-id="f4942-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f4942-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="f4942-105">Suggestion</span></span>

<span data-ttu-id="f4942-106">Эта проблема была устранена в .NET Framework 4.5.2 и может быть решена путем обновления до этой версии (или более поздней) платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f4942-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="f4942-107">Кроме того, пользователи по-прежнему могут перетаскивать полосы прокрутки к последним элементам в этих коллекциях, однако для успешного выполнения этой задачи это может потребоваться сделать дважды.</span><span class="sxs-lookup"><span data-stu-id="f4942-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="f4942-108">name</span><span class="sxs-lookup"><span data-stu-id="f4942-108">Name</span></span>    | <span data-ttu-id="f4942-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f4942-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f4942-110">Область</span><span class="sxs-lookup"><span data-stu-id="f4942-110">Scope</span></span>   |<span data-ttu-id="f4942-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f4942-111">Minor</span></span>|
|<span data-ttu-id="f4942-112">Version</span><span class="sxs-lookup"><span data-stu-id="f4942-112">Version</span></span>|<span data-ttu-id="f4942-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f4942-113">4.5</span></span>|
|<span data-ttu-id="f4942-114">Type</span><span class="sxs-lookup"><span data-stu-id="f4942-114">Type</span></span>|<span data-ttu-id="f4942-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f4942-115">Runtime</span></span>|
