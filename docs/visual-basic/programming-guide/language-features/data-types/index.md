---
title: Типы данных
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
ms.openlocfilehash: 928d7fb6a40873641ae3e91e057c272b946a0091
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393718"
---
# <a name="data-types-in-visual-basic"></a>Типы данных в Visual Basic
*Тип данных* программного элемента определяет данные, которые он может содержать, а также способ их хранения. Типы данных применяются ко всем значениям, которые могут храниться в памяти компьютера или участвовать в вычислении выражения. Все переменные, литералы, константы, перечисления, свойства, параметры и аргументы процедуры, а также возвращаемые значения процедуры относятся к определенному типу данных.  
  
## <a name="declared-data-types"></a>Объявленные типы данных  
 Программный элемент определяется с помощью оператора объявления, а его тип данных указывается с помощью предложения `As`. В таблице ниже приведены инструкции, которые используются для объявления разных элементов.  
  
|Программный элемент|Объявление типа данных|  
|-------------------------|---------------------------|  
|Переменная|В [операторе Dim](../../../language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Литерал|С помощью символа типа литерала; см. [символы типов](type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Константа|В [операторе Const](../../../language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Перечисление|В [операторе Enum](../../../language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Свойство|В [операторе Property](../../../language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Параметр процедуры|В [операторе Sub](../../../language-reference/statements/sub-statement.md), [инструкции Function](../../../language-reference/statements/function-statement.md) или [инструкции Operator](../../../language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Аргумент процедуры|В вызывающем коде; все аргументы являются уже объявленными элементами программирования или выражениями, содержащими объявленные элементы<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Возвращаемое значение процедуры|В [инструкции Function](../../../language-reference/statements/function-statement.md) или [инструкции Operator](../../../language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 См. список [типов данных](../../../language-reference/data-types/index.md) Visual Basic  
  
## <a name="see-also"></a>См. также раздел

- [Символы типов](type-characters.md)
- [Простые типы данных](elementary-data-types.md)
- [Составные типы данных](composite-data-types.md)
- [Generic Types in Visual Basic](generic-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Преобразование типов в Visual Basic](type-conversions.md)
- [Структуры](structures.md)
- [Кортежи](tuples.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Типы данных](../../../language-reference/data-types/index.md)
- [Эффективное использование типов данных](efficient-use-of-data-types.md)
