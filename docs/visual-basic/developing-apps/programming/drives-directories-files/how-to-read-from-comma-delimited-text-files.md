---
title: Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: ba62a0226a1a83326cbc7ab393d135763a7c7cb2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411646"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a>Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic

Объект `TextFieldParser` позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов. Свойство `TextFieldType` определяет, является ли файл файлом с разделителями или с полями фиксированной ширины текста.  
  
### <a name="to-parse-a-comma-delimited-text-file"></a>Анализ текстового файла с разделителями-запятыми  
  
1. Создайте `TextFieldParser`. Следующий код создает объект `TextFieldParser` с именем `MyReader` и открывает файл `test.txt`.  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. Определение тип `TextField` и разделитель. Следующий код определяет для свойства `TextFieldType` значение `Delimited`, а для разделителя — ",".  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. Просмотрите поля в файле. Если какие-либо строки повреждены, выведите сообщение об ошибке и продолжите анализ. Следующий код выполняет цикл по файлу, отображая каждое поле по очереди и сообщая обо всех полях с неправильным форматированием.  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. Закройте блоки `While` и `Using` операторами `End While` и `End Using`.  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a>Пример  

 В этом примере производится чтение данных из файла `test.txt`.  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 При следующих условиях возможно возникновение исключения:  
  
- Строка не может быть проанализирована с использованием указанного формата (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Сообщение исключения содержит строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> содержит текст, который содержится в этой строке.  
  
- Указанный файл не существует (<xref:System.IO.FileNotFoundException>).  
  
- Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу. (<xref:System.Security.SecurityException>).  
  
- Слишком длинный путь (<xref:System.IO.PathTooLongException>).  
  
- Пользователь не имеет необходимых разрешений для доступа к файлу (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](how-to-read-from-fixed-width-text-files.md)
- [Практическое руководство. Чтение из текстовых файлов различных форматов](how-to-read-from-text-files-with-multiple-formats.md)
- [Анализ текстовых файлов с помощью объекта TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
- [Пошаговое руководство. Операции с файлами и каталогами в Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](troubleshooting-reading-from-and-writing-to-text-files.md)
