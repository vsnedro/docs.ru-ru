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
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms

Часто в создаваемых приложениях Windows требуется предлагать пользователю выбрать папку, как правило, для сохранения набора файлов. Компонент Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> позволяет легко выполнить эту задачу.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Выбор папки с помощью компонента FolderBrowserDialog

1. В процедуре проверьте <xref:System.Windows.Forms.FolderBrowserDialog> свойство компонента, <xref:System.Windows.Forms.Form.DialogResult%2A> чтобы увидеть, как было закрыто диалоговое окно, и получите значение <xref:System.Windows.Forms.FolderBrowserDialog> <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Свойства компонента.

2. Если необходимо задать самую верхнюю папку, которая будет отображаться в представлении в виде дерева диалогового окна, задайте <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойство, которое принимает член <xref:System.Environment.SpecialFolder> перечисления.

3. Кроме того, можно задать <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> свойство, которое указывает текстовую строку, отображаемую в верхней части представления в виде дерева обозревателя папок.

    В приведенном ниже примере <xref:System.Windows.Forms.FolderBrowserDialog> компонент используется для выбора папки, аналогично при создании проекта в Visual Studio и появлении запроса на выбор папки для ее сохранения. В этом примере имя папки отображается в <xref:System.Windows.Forms.TextBox> элементе управления в форме. Рекомендуется размещать расположение в редактируемой области, например в <xref:System.Windows.Forms.TextBox> элементе управления, чтобы пользователи могли изменять свой выбор в случае ошибки или других проблем. В этом примере предполагается наличие формы с <xref:System.Windows.Forms.FolderBrowserDialog> компонентом и <xref:System.Windows.Forms.TextBox> элементом управления.

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
    > Чтобы использовать этот класс, сборке требуется уровень привилегий, предоставляемый <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> свойством, которое является частью <xref:System.Security.Permissions.FileIOPermissionAccess> перечисления. При выполнении в контексте частичного доверия процесс может выдавать исключение из-за недостаточных привилегий. Дополнительные сведения см. в разделе [Code Access Security Basics](../../misc/code-access-security-basics.md).

Сведения о том, как сохранять файлы, см. в разделе [Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Общие сведения о компоненте FolderBrowserDialog (Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [Компонент FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
