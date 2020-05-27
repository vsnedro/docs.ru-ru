---
ms.openlocfilehash: bba74f26eafd52b966928835d5003d03af1eabdc
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721338"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`, появившийся в .NET Framework 4.6.1, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Framework 4.6.1, при нажатии клавиш <kbd>CTRL</kbd> + <kbd>A</kbd> в элементе управления <xref:System.Windows.Forms.TextBox> выделяется весь текст. В .NET Framework 4.6 и более ранних версиях при нажатии клавиш <kbd>CTRL</kbd> + <kbd>A</kbd> выделение всего текста не происходило, если свойства [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) и <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> имели значение `true`. Параметр совместимости `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` появился в .NET Framework 4.6.1 для восстановления прежнего поведения. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

В .NET Core параметр `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- None

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
