---
ms.openlocfilehash: 7a6b0b15de4295506ff03b8566c06010b918566c
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158409"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a>Теперь методы WinForms вызывают исключение ArgumentNullException

Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentNullException> для аргументов NULL в ситуациях, где ранее вызывали <xref:System.NullReferenceException>.

#### <a name="change-description"></a>Описание изменений

Ранее некоторые методы Windows Forms вызвали <xref:System.NullReferenceException> при передаче аргумента, который имел значение NULL. Начиная с .NET 5.0 вместо этого такие методы вызывают <xref:System.ArgumentNullException> для аргументов NULL.

Вызов <xref:System.ArgumentNullException> соответствует поведению среды выполнения .NET. Это также улучшает процесс отладки, четко указывая, что аргумент имеет значение NULL и какой именно это аргумент.

#### <a name="version-introduced"></a>Представленная версия

Предварительная версия 1 .NET 5.0
Предварительная версия 2 .NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы вызываете любой из этих методов и код в данный момент перехватывает <xref:System.NullReferenceException> для аргументов NULL, вместо этого перехватите <xref:System.ArgumentNullException>. Кроме того, рекомендуется обновить код, чтобы предотвратить передачу аргументов NULL в перечисленные методы.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

Начиная с предварительной версии 1 .NET 5.0:

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

Начиная с предварительной версии 2 .NET 5.0:

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (только для параметра <xref:System.IO.Stream>)

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
