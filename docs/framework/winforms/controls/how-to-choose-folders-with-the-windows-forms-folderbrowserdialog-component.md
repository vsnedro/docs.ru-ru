---
title: Выбор папок с помощью компонента FolderBrowserDialog
description: Узнайте, как использовать компонент Windows Forms FolderBrowserDialog в создаваемых приложениях Windows, чтобы предлагать пользователям выбрать папку.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 11d01bbaec3b82bc221960ebab5e33ca1aa302db
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903679"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="24e2f-103">Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24e2f-103">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="24e2f-104">Часто в создаваемых приложениях Windows требуется предлагать пользователю выбрать папку, как правило, для сохранения набора файлов.</span><span class="sxs-lookup"><span data-stu-id="24e2f-104">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="24e2f-105">Компонент Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> позволяет легко выполнить эту задачу.</span><span class="sxs-lookup"><span data-stu-id="24e2f-105">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="24e2f-106">Выбор папки с помощью компонента FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="24e2f-106">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="24e2f-107">В процедуре проверьте <xref:System.Windows.Forms.FolderBrowserDialog> свойство компонента, <xref:System.Windows.Forms.Form.DialogResult%2A> чтобы увидеть, как было закрыто диалоговое окно, и получите значение <xref:System.Windows.Forms.FolderBrowserDialog> <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Свойства компонента.</span><span class="sxs-lookup"><span data-stu-id="24e2f-107">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="24e2f-108">Если необходимо задать самую верхнюю папку, которая будет отображаться в представлении в виде дерева диалогового окна, задайте <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойство, которое принимает член <xref:System.Environment.SpecialFolder> перечисления.</span><span class="sxs-lookup"><span data-stu-id="24e2f-108">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="24e2f-109">Кроме того, можно задать <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> свойство, которое указывает текстовую строку, отображаемую в верхней части представления в виде дерева обозревателя папок.</span><span class="sxs-lookup"><span data-stu-id="24e2f-109">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="24e2f-110">В приведенном ниже примере <xref:System.Windows.Forms.FolderBrowserDialog> компонент используется для выбора папки, аналогично при создании проекта в Visual Studio и появлении запроса на выбор папки для ее сохранения.</span><span class="sxs-lookup"><span data-stu-id="24e2f-110">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="24e2f-111">В этом примере имя папки отображается в <xref:System.Windows.Forms.TextBox> элементе управления в форме.</span><span class="sxs-lookup"><span data-stu-id="24e2f-111">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="24e2f-112">Рекомендуется размещать расположение в редактируемой области, например в <xref:System.Windows.Forms.TextBox> элементе управления, чтобы пользователи могли изменять свой выбор в случае ошибки или других проблем.</span><span class="sxs-lookup"><span data-stu-id="24e2f-112">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="24e2f-113">В этом примере предполагается наличие формы с <xref:System.Windows.Forms.FolderBrowserDialog> компонентом и <xref:System.Windows.Forms.TextBox> элементом управления.</span><span class="sxs-lookup"><span data-stu-id="24e2f-113">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

    ```vb
    Public Sub ChooseFolder()
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then
            TextBox1.Text = FolderBrowserDialog1.SelectedPath
        End If
    End Sub
    ```

    ```csharp
    public void ChooseFolder()
    {
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)
        {
            textBox1.Text = folderBrowserDialog1.SelectedPath;
        }
    }
    ```

    ```cpp
    public:
       void ChooseFolder()
       {
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)
          {
             textBox1->Text = folderBrowserDialog1->SelectedPath;
          }
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="24e2f-114">Чтобы использовать этот класс, сборке требуется уровень привилегий, предоставляемый <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> свойством, которое является частью <xref:System.Security.Permissions.FileIOPermissionAccess> перечисления.</span><span class="sxs-lookup"><span data-stu-id="24e2f-114">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="24e2f-115">При выполнении в контексте частичного доверия процесс может выдавать исключение из-за недостаточных привилегий.</span><span class="sxs-lookup"><span data-stu-id="24e2f-115">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="24e2f-116">Дополнительные сведения см. в разделе [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="24e2f-116">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="24e2f-117">Сведения о том, как сохранять файлы, см. в разделе [Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="24e2f-117">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24e2f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="24e2f-118">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="24e2f-119">Общие сведения о компоненте FolderBrowserDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="24e2f-119">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="24e2f-120">Компонент FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="24e2f-120">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
