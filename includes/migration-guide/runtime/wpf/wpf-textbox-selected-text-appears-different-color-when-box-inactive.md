---
ms.openlocfilehash: c01705002ad87a12389078d75ffd0f91f934d36e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496942"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="991da-101">Выделенный текст в элементе управления TextBox WPF будет отображаться другим цветом, если текстовое поле неактивно</span><span class="sxs-lookup"><span data-stu-id="991da-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="991da-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="991da-102">Details</span></span>

<span data-ttu-id="991da-103">В .NET Framework 4.5, если элемент управления текстовым полем WPF неактивен (в нем отсутствует фокус), выбранный текст внутри поля будет отображаться цветом, отличным от того, когда элемент управления является активным.</span><span class="sxs-lookup"><span data-stu-id="991da-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="991da-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="991da-104">Suggestion</span></span>

<span data-ttu-id="991da-105">Чтобы восстановить прежнее поведение (.NET Framework 4.0), задайте для свойства <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> значение <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="991da-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="991da-106">name</span><span class="sxs-lookup"><span data-stu-id="991da-106">Name</span></span>    | <span data-ttu-id="991da-107">Значение</span><span class="sxs-lookup"><span data-stu-id="991da-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="991da-108">Область</span><span class="sxs-lookup"><span data-stu-id="991da-108">Scope</span></span>   |<span data-ttu-id="991da-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="991da-109">Edge</span></span>|
|<span data-ttu-id="991da-110">Version</span><span class="sxs-lookup"><span data-stu-id="991da-110">Version</span></span>|<span data-ttu-id="991da-111">4.5</span><span class="sxs-lookup"><span data-stu-id="991da-111">4.5</span></span>|
|<span data-ttu-id="991da-112">Type</span><span class="sxs-lookup"><span data-stu-id="991da-112">Type</span></span>|<span data-ttu-id="991da-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="991da-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="991da-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="991da-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
