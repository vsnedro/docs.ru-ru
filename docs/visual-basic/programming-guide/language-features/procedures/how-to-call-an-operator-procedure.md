---
title: Практическое руководство. Вызов процедуры оператора
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: fa2bc5417b8b917ff48502a5bd0a4daa21fab67e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388573"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры оператора (Visual Basic)
Для вызова процедуры оператора используется символ оператора в выражении. В случае оператора преобразования вызывается [Функция CType](../../../language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.  
  
 Процедуры оператора не вызываются явным образом. Вы просто используете оператор или `CType` функцию в операторе присваивания или выражении так же, как обычно используется оператор. Visual Basic выполняет вызов процедуры оператора.  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
### <a name="to-call-an-operator-procedure"></a>Вызов процедуры оператора  
  
1. Используйте символ оператора в выражении обычным образом.  
  
2. Убедитесь, что типы данных операндов подходят для оператора, и в правильном порядке.  
  
3. Оператор влияет на значение выражения, как и ожидалось.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Вызов процедуры оператора преобразования  
  
1. Используйте `CType` внутри выражения.  
  
2. Убедитесь, что типы данных операндов подходят для преобразования, и в правильном порядке.  
  
3. `CType`вызывает процедуру оператора преобразования и возвращает преобразованное значение.  
  
## <a name="example"></a>Пример  
 Следующий пример создает две <xref:System.TimeSpan> структуры, добавляет их вместе и сохраняет результат в третьей <xref:System.TimeSpan> структуре. <xref:System.TimeSpan>Структура определяет процедуры операторов для перегрузки нескольких стандартных операторов.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Поскольку <xref:System.TimeSpan> перегружает Стандартный `+` оператор, предыдущий пример вызывает процедуру оператора при вычислении значения `combinedSpan` .  
  
 Пример вызова процедуры оператора диалога см. [в разделе как использовать класс, определяющий операторы](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compile-the-code"></a>Компиляция кода  
 Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать.  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Оператор Structure](../../../language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../data-types/how-to-declare-a-structure.md)
- [Явные и неявные преобразования](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
