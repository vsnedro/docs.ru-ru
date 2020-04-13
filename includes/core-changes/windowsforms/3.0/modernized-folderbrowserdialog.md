---
ms.openlocfilehash: 645df8080abd21e4db95903a301a36b79a698858
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888143"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="0e125-101">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="0e125-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="0e125-102">В приложениях Windows Forms для .NET Core в элемент управления <xref:System.Windows.Forms.FolderBrowserDialog> внесены изменения.</span><span class="sxs-lookup"><span data-stu-id="0e125-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0e125-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="0e125-103">Change description</span></span>

<span data-ttu-id="0e125-104">В Windows Forms в .NET Framework для элемента управления <xref:System.Windows.Forms.FolderBrowserDialog> используется следующее диалоговое окно:</span><span class="sxs-lookup"><span data-stu-id="0e125-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl в .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="0e125-106">В .NET Core 3.0 в Windows Forms используется более новый элемент управления на основе COM, появившийся в Windows Vista:</span><span class="sxs-lookup"><span data-stu-id="0e125-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl в .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="0e125-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="0e125-108">Version introduced</span></span>

<span data-ttu-id="0e125-109">3,0</span><span class="sxs-lookup"><span data-stu-id="0e125-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0e125-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="0e125-110">Recommended action</span></span>

<span data-ttu-id="0e125-111">Диалоговое окно будет обновлено автоматически.</span><span class="sxs-lookup"><span data-stu-id="0e125-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="0e125-112">Если вы хотите оставить исходное диалоговое окно, перед отображением диалогового окна задайте для свойства <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> значение `false`, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="0e125-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="0e125-113">Категория</span><span class="sxs-lookup"><span data-stu-id="0e125-113">Category</span></span>

<span data-ttu-id="0e125-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e125-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0e125-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0e125-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
