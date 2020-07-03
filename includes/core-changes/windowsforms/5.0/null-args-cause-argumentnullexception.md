---
ms.openlocfilehash: 00f89e6ae49982917fa7591c3283adec3947eed2
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365659"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a>Теперь методы WinForms вызывают исключение ArgumentNullException

Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentNullException> для аргументов NULL в ситуациях, где ранее вызывали <xref:System.NullReferenceException>.

#### <a name="change-description"></a>Описание изменений

Ранее некоторые методы Windows Forms вызвали <xref:System.NullReferenceException> при передаче аргумента, который имел значение NULL. Начиная с .NET 5.0, вместо этого такие методы вызывают <xref:System.ArgumentNullException> для аргументов NULL.

Вызов <xref:System.ArgumentNullException> соответствует поведению среды выполнения .NET. Это также улучшает процесс отладки, четко указывая, что аргумент имеет значение NULL и какой именно это аргумент.

#### <a name="version-introduced"></a>Представленная версия

.NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы вызываете любой из этих методов и код в данный момент перехватывает <xref:System.NullReferenceException> для аргументов NULL, вместо этого перехватите <xref:System.ArgumentNullException>. Кроме того, рекомендуется обновить код, чтобы предотвратить передачу аргументов NULL в перечисленные методы.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

В следующей таблице перечислены затронутые методы и параметры:

> [!div class="mx-tdBreakAll"]
> | Метод | Имя параметра | Добавлено в версии |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | 5.0 Предварительная версия 1 |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | 5.0, предварительная версия 2 |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | 5.0, предварительная версия 2 |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | 5.0, предварительная версия 5 |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | 5.0, предварительная версия 5 |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | 5.0, предварительная версия 5 |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | 5.0, предварительная версия 5 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | 5.0, предварительная версия 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | `owner`, `value` | 5.0, предварительная версия 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | `owner`, `value` | 5.0, предварительная версия 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | 5.0, предварительная версия 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | 5.0, предварительная версия 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | 5.0, предварительная версия 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination`q` | 5.0, предварительная версия 6 |

<!-- 

#### Affected APIs

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
- `M:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)`

-->
