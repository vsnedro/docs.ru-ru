---
title: Практическое руководство. Использование класса, в котором определяются операторы
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 083916a420bf4ad182536363ea46448f6b4c1da5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071356"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)

При использовании класса или структуры, определяющей собственные операторы, можно получить доступ к этим операторам из Visual Basic.  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
## <a name="example"></a>Пример  

 В следующем примере осуществляется доступ к структуре SQL <xref:System.Data.SqlTypes.SqlString> , которая определяет операторы преобразования ([Функция CType](../../../language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и строкой Visual Basic. Используйте `CType(` *строковое выражение SQL*, `String)` чтобы преобразовать строку SQL в Visual Basic строку и `CType(` *Visual Basic строковое выражение* <xref:System.Data.SqlTypes.SqlString> `)` для преобразования в другом направлении.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <xref:System.Data.SqlTypes.SqlString>Структура определяет оператор преобразования ([Функция CType](../../../language-reference/functions/ctype-function.md)) из `String` в <xref:System.Data.SqlTypes.SqlString> и другой из <xref:System.Data.SqlTypes.SqlString> в `String` . Инструкция, которая назначается `title` для `jobTitle` использования первого оператора, а <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов функции использует второй.  
  
## <a name="compile-the-code"></a>Компиляция кода  

 Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать. Не следует считать, что класс или структура определили все операторы, доступные для перегрузки. Список доступных операторов см. в разделе Оператор [operator](../../../language-reference/statements/operator-statement.md).  
  
 Включите соответствующую `Imports` инструкцию для строки SQL в начало исходного файла (в данном случае <xref:System.Data.SqlTypes> ).  
  
 Проект должен содержать ссылки на System. Data и System.XML.  
  
## <a name="see-also"></a>См. также

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Оператор Structure](../../../language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../data-types/how-to-declare-a-structure.md)
- [Явные и неявные преобразования](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
