---
title: Разбор строки <number> с помощью текущего параметра FieldWidths невозможен
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_MalFormedFixedWidthLine
ms.assetid: 84e14245-dfdf-4b62-8b84-e83a31608899
ms.openlocfilehash: bd7c372f3cfee3babe4b3fdf190bf8ed87dab6db
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100377"
---
# <a name="line-number-cannot-be-parsed-using-the-current-fieldwidths"></a>Разбор строки \<number> с помощью текущего параметра FieldWidths невозможен

Указанная строка не может быть проанализирована, так как ее поля имеют ширину, отличную от указанной.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Настройте `FieldWidths` так, чтобы строка могла быть проанализирована правильно, или вставьте код обработки исключения, чтобы обработать строку.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Чтение из текстовых файлов различных форматов](../developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [My. Computer. FileSystem. OpenTextFieldParser](xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A)
- [Анализ текстовых файлов с помощью объекта TextFieldParser](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
- [Свойство TextFieldParser.FieldWidths](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A)
- [Метод TextFieldParser.SetFieldWidths](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A)
