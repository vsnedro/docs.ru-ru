---
title: Как открыть файлы с помощью компонента OpenFileDialog
ms.date: 02/11/2019
description: Узнайте, как использовать компонент OpenFileDialog, чтобы открыть диалоговое окно Windows для обзора и выбора файлов.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904433"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Как открыть файлы с помощью OpenFileDialog

<xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>Компонент открывает диалоговое окно Windows для обзора и выбора файлов. Чтобы открыть и прочитать выбранные файлы, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> метод или создать экземпляр <xref:System.IO.StreamReader?displayProperty=nameWithType> класса. В следующих примерах показаны оба подхода.

В .NET Framework для получения или задания <xref:System.Windows.Forms.FileDialog.FileName%2A> свойства требуется уровень привилегий, предоставляемый <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> классом. В примерах выполняется <xref:System.Security.Permissions.FileIOPermission> Проверка разрешений и может вызываться исключение из-за недостаточных привилегий при выполнении в контексте частичного доверия. Дополнительные сведения см. в статье [основы управления доступом для кода](../../misc/code-access-security-basics.md).

Вы можете собрать и запустить эти примеры как .NET Framework приложения из командной строки C# или Visual Basic. Дополнительные сведения см. в разделе [Построение из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Начиная с .NET Core 3,0, можно также создавать и запускать примеры как приложения Windows .NET Core из папки с файлом проекта .NET Core Windows Forms * \<folder name> . csproj* .

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Пример. чтение файла в виде потока с помощью StreamReader  
  
В следующем примере используется <xref:System.Windows.Forms.Button> обработчик событий Windows Forms элемента управления <xref:System.Windows.Forms.Control.Click> для открытия <xref:System.Windows.Forms.OpenFileDialog> с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метода. После того как пользователь выберет файл и нажмет **кнопку ОК**, экземпляр <xref:System.IO.StreamReader> класса считывает файл и отображает его содержимое в текстовом поле формы. Дополнительные сведения о чтении из файловых потоков см <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> . в разделе и <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Пример. Открытие файла из отфильтрованного выделенного фрагмента с помощью OpenFile

В следующем примере <xref:System.Windows.Forms.Button> обработчик событий элемента управления используется <xref:System.Windows.Forms.Control.Click> для открытия <xref:System.Windows.Forms.OpenFileDialog> с фильтром, который отображает только текстовые файлы. После того как пользователь выберет текстовый файл и нажмет **кнопку ОК**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> для открытия файла в блокноте используется метод.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.OpenFileDialog>
- [Компонент OpenFileDialog](openfiledialog-component-windows-forms.md)
