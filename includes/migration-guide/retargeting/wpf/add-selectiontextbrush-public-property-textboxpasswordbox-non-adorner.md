---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616308"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Добавление открытого свойства SelectionTextBrush при выделении текстового поля или поля пароля без графического элемента

#### <a name="details"></a>Подробнее

В приложениях WPF при [выделении текста без графических элементов](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) для <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox> разработчики теперь могут задать новое свойство SelectionTextBrush, чтобы изменить отрисовку выбранного текста.  По умолчанию этот цвет меняется с <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Если выделение текста без использования графического элемента не включено, это свойство ничего не делает.

#### <a name="suggestion"></a>Предложение

Если выделение текста без графического элемента включено, вы можете использовать свойство <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> и <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> для изменения внешнего вида выбранного текста. Это можно сделать с помощью XAML:

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.8         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)
- [System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)
