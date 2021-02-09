---
description: 'Подробнее о следующем: Практическое руководство. Запись текста в файлы в каталоге "Мои документы" в Visual Basic'
title: Практическое руководство. Запись текста в файлы в каталоге "Мои документы"
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: da7472e9d8d4c39509dda814a18e7c0149236eeb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797371"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a>Практическое руководство. Запись текста в файлы в каталоге "Мои документы" в Visual Basic

Объект `My.Computer.FileSystem.SpecialDirectories` позволяет получить доступ к специальным каталогам, таким как каталог **Мои документы**.  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a>Запись новых текстовых файлов в каталог "Мои документы"  
  
1. Укажите путь в свойстве `My.Computer.FileSystem.SpecialDirectories.MyDocuments`.  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. Используйте метод `WriteAllText` для записи текста в указанный файл.  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a>Пример  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 Замените имя `test.txt` на имя файла, в который требуется выполнить запись.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 Этот код возвращает все исключения, которые могут произойти при записи текста в файл. Можно уменьшить вероятность возникновения исключений с помощью элементов управления Windows Forms, таких как компоненты [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) и [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms), которые позволяют пользователям выбирать только допустимые имена файлов. Однако использование этих элементов управления не гарантирует полную надежность. В период между моментом выбора пользователем файла и моментом выполнения кода файловая система может измениться. Таким образом, при работе с файлами обработка исключений почти всегда является необходимой.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  

 Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа. Дополнительные сведения см. в разделе [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).  
  
 В этом примере создается новый файл. Если приложение создает файл, оно должно иметь разрешение на создание файла в соответствующем каталоге. Для задания разрешений используются списки управления доступом. Если файл уже существует, приложению требуется лишь разрешение на запись (с более низким уровнем). Для повышения безопасности рекомендуется по возможности создавать файлы во время развертывания и предоставлять доступ на чтение только к одному файлу, а не доступ к каталогу с разрешением на создание. По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в корневую папку или папку **Program Files**. Дополнительные сведения см. в разделе [Общие сведения о технологии ACL](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
