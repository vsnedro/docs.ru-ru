---
description: 'Дополнительные сведения: все поля ширины полей, за исключением последнего элемента, должны быть больше нуля'
title: Все поля, за исключением последнего элемента, должны иметь ширину больше нуля
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: cf2edb21f017031c7dd333893d554353eceebe73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787387"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Все поля, за исключением последнего элемента, должны иметь ширину больше нуля

Все поля, за исключением последнего элемента, должны иметь ширину больше нуля. Ширина поля, меньшая или равная нулю в последнем элементе, указывает, что поле имеет переменную длину.  
  
 Операция не была выполнена, так как ширина поля, отличного от последнего элемента, задана равной нулю или меньше. Ширина поля, меньшая или равная нулю, может использоваться в последнем элементе для указания на то, что последнее поле имеет переменную длину, но не может использоваться как любой другой элемент.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Задайте для ширины поля корректное значение.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
