---
title: Разбор строки <number> с помощью текущего параметра FieldWidths невозможен
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_MalFormedFixedWidthLine
ms.assetid: 84e14245-dfdf-4b62-8b84-e83a31608899
ms.openlocfilehash: bd6fc431a4a943a3a0022e8e75c834a49b952a66
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402139"
---
# <a name="line-number-cannot-be-parsed-using-the-current-fieldwidths"></a>Разбор строки \<number> с помощью текущего параметра FieldWidths невозможен
Указанная строка не может быть проанализирована, так как ее поля имеют ширину, отличную от указанной.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Настройте `FieldWidths` так, чтобы строка могла быть проанализирована правильно, или вставьте код обработки исключения, чтобы обработать строку.  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Чтение из текстовых файлов различных форматов](../developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [My. Computer. FileSystem. OpenTextFieldParser](xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A)
- [Анализ текстовых файлов с помощью объекта TextFieldParser](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
- [Свойство TextFieldParser.FieldWidths](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A)
- [Метод TextFieldParser.SetFieldWidths](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A)
