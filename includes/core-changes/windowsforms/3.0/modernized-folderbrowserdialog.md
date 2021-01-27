---
ms.openlocfilehash: 27c6353f8f71254a505b434921f4b1e61e64cdda
ms.sourcegitcommit: 2b878d7011306b215dbf3d5dc9c1e78355a6dcd5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "98758168"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Модернизация FolderBrowserDialog

В приложениях Windows Forms для .NET Core в элемент управления <xref:System.Windows.Forms.FolderBrowserDialog> внесены изменения.

#### <a name="change-description"></a>Описание изменений

В Windows Forms в .NET Framework для элемента управления <xref:System.Windows.Forms.FolderBrowserDialog> используется следующее диалоговое окно:

![FolderBrowserDialogControl в .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

В .NET Core 3.0 в Windows Forms используется более новый элемент управления на основе COM, появившийся в Windows Vista:

![FolderBrowserDialogControl в .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Представленная версия

3,0

#### <a name="recommended-action"></a>Рекомендованное действие

Диалоговое окно будет обновлено автоматически.

Если вы хотите оставить исходное диалоговое окно, перед отображением диалогового окна задайте для свойства <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> значение `false`, как показано в следующем фрагменте кода:

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

#### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
