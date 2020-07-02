---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620708"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="95cb3-101">Выделенный текст в элементе управления TextBox WPF будет отображаться другим цветом, если текстовое поле неактивно</span><span class="sxs-lookup"><span data-stu-id="95cb3-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="95cb3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="95cb3-102">Details</span></span>

<span data-ttu-id="95cb3-103">В .NET Framework 4.5, если элемент управления текстовым полем WPF неактивен (в нем отсутствует фокус), выбранный текст внутри поля будет отображаться цветом, отличным от того, когда элемент управления является активным.</span><span class="sxs-lookup"><span data-stu-id="95cb3-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="95cb3-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="95cb3-104">Suggestion</span></span>

<span data-ttu-id="95cb3-105">Чтобы восстановить прежнее поведение (.NET Framework 4.0), задайте для свойства <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> значение <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="95cb3-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="95cb3-106">name</span><span class="sxs-lookup"><span data-stu-id="95cb3-106">Name</span></span>    | <span data-ttu-id="95cb3-107">Значение</span><span class="sxs-lookup"><span data-stu-id="95cb3-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="95cb3-108">Область</span><span class="sxs-lookup"><span data-stu-id="95cb3-108">Scope</span></span>   |<span data-ttu-id="95cb3-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="95cb3-109">Edge</span></span>|
|<span data-ttu-id="95cb3-110">Version</span><span class="sxs-lookup"><span data-stu-id="95cb3-110">Version</span></span>|<span data-ttu-id="95cb3-111">4.5</span><span class="sxs-lookup"><span data-stu-id="95cb3-111">4.5</span></span>|
|<span data-ttu-id="95cb3-112">Type</span><span class="sxs-lookup"><span data-stu-id="95cb3-112">Type</span></span>|<span data-ttu-id="95cb3-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="95cb3-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95cb3-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="95cb3-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
