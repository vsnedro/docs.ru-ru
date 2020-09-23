---
title: Практическое руководство. Определение оператора преобразования
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 2fabcf6c6ceb38fe77d4eed4f02dcb5a5e447bf1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085676"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Практическое руководство. Определение оператора преобразования (Visual Basic)

Если вы определили класс или структуру, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных (например `Integer` ,, `Double` или `String` ).  
  
 Определите преобразование типа как процедуру [функции CType](../../../language-reference/functions/ctype-function.md) в классе или структуре. Все процедуры преобразования должны иметь `Public Shared` значение, и каждая из них должна указывать [расширение](../../../language-reference/modifiers/widening.md) или [сужение](../../../language-reference/modifiers/narrowing.md).  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
## <a name="example"></a>Пример  

 В следующем примере определяются операторы преобразования между структурой `digit` и `Byte` .  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Структуру можно проверить `digit` с помощью следующего кода.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Оператор Structure](../../../language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../data-types/how-to-declare-a-structure.md)
- [Явные и неявные преобразования](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
