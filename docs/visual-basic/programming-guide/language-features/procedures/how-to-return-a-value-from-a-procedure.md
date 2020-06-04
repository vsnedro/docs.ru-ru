---
title: Практическое руководство. Возврат значения из процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 917e52b711645fbf94a132216a3fa90b0dfc15b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414328"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Практическое руководство. Возврат значения из процедуры (Visual Basic)
`Function`Процедура возвращает значение в вызывающий код, выполняя инструкцию или выполняя инструкцию `Return` `Exit Function` или `End Function` .  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Возврат значения с помощью оператора return  
  
1. Поместите `Return` оператор в точку завершения задачи процедуры.  
  
2. Используйте `Return` ключевое слово с выражением, которое возвращает значение, которое необходимо вернуть в вызывающий код.  
  
3. В одной и той же процедуре можно использовать несколько операторов `Return`.  
  
     Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника и возвращает ее в вызывающий код.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     В следующем примере показан типичный вызов метода `hypotenuse` , в котором хранится возвращаемое значение.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Возврат значения с помощью функции exit или функции End  
  
1. По крайней мере в одном месте `Function` процедуры присвойте значение имени процедуры.  
  
2. При выполнении `Exit Function` `End Function` инструкции или Visual Basic возвращает последнее значение, назначенное имени процедуры.  
  
3. В одной и той же процедуре можно использовать несколько операторов `Exit Function` и одновременно использовать операторы `Return` и `Exit Function`.  
  
4. В процедуре может быть только одна `End Function` инструкция `Function` .  
  
     Дополнительные сведения и пример см. в разделе "возвращаемое значение" в [операторе Function](../../../language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../language-reference/statements/function-statement.md)
- [Оператор Return](../../../language-reference/statements/return-statement.md)
- [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
