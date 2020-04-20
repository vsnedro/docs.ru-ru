---
ms.openlocfilehash: fc0eec26073c299887b4748d0ad37e21c7294e84
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275303"
---
### <a name="winforms-apis-now-throw-argumentnullexception"></a><span data-ttu-id="fe886-101">Теперь API WinForms выдают исключение ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="fe886-101">WinForms APIs now throw ArgumentNullException</span></span>

<span data-ttu-id="fe886-102">Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentNullException> для аргументов NULL в ситуациях, где ранее вызывали <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="fe886-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fe886-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="fe886-103">Change description</span></span>

<span data-ttu-id="fe886-104">Ранее некоторые методы Windows Forms вызвали <xref:System.NullReferenceException> при передаче аргумента, который имел значение NULL.</span><span class="sxs-lookup"><span data-stu-id="fe886-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="fe886-105">Начиная с .NET 5.0 вместо этого такие методы вызывают <xref:System.ArgumentNullException> для аргументов NULL.</span><span class="sxs-lookup"><span data-stu-id="fe886-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="fe886-106">Вызов <xref:System.ArgumentNullException> соответствует поведению среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="fe886-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="fe886-107">Это также улучшает процесс отладки, четко указывая, что аргумент имеет значение NULL и какой именно это аргумент.</span><span class="sxs-lookup"><span data-stu-id="fe886-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fe886-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="fe886-108">Version introduced</span></span>

<span data-ttu-id="fe886-109">Предварительная версия 1 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="fe886-109">.NET 5.0 Preview 1\</span></span>
<span data-ttu-id="fe886-110">Предварительная версия 2 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="fe886-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fe886-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="fe886-111">Recommended action</span></span>

<span data-ttu-id="fe886-112">Если вы вызываете любой из этих методов и код в данный момент перехватывает <xref:System.NullReferenceException> для аргументов NULL, вместо этого перехватите <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="fe886-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="fe886-113">Кроме того, рекомендуется обновить код, чтобы предотвратить передачу аргументов NULL в перечисленные методы.</span><span class="sxs-lookup"><span data-stu-id="fe886-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="fe886-114">Категория</span><span class="sxs-lookup"><span data-stu-id="fe886-114">Category</span></span>

<span data-ttu-id="fe886-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe886-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fe886-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="fe886-116">Affected APIs</span></span>

<span data-ttu-id="fe886-117">Начиная с предварительной версии 1 .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="fe886-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="fe886-118">Начиная с предварительной версии 2 .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="fe886-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="fe886-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (только для параметра <xref:System.IO.Stream>)</span><span class="sxs-lookup"><span data-stu-id="fe886-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`

-->
