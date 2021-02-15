---
description: Дополнительные сведения о том, как создать процедуру, возвращающую значение (Visual Basic).
title: Практическое руководство. Создание процедуры, возвращающей значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: fa2ea50febd1cc4e7aecf1e6f5cca671789b36fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100467060"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)

Для `Function` возврата значения в вызывающий код используется процедура.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение  
  
1. За пределами любой другой процедуры используйте `Function` оператор, за которым следует `End Function` оператор.  
  
2. В `Function` инструкции используйте `Function` ключевое слово с именем процедуры, а затем список параметров в круглых скобках.  
  
3. Используйте круглые скобки с `As` предложением, чтобы указать тип данных возвращаемого значения.  
  
4. Поместите операторы кода процедуры между `Function` `End Function` операторами и.  
  
5. Используйте `Return` оператор, чтобы вернуть значение в вызывающий код.  
  
     Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     В следующем примере показан типичный вызов метода `hypotenuse` .  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../language-reference/statements/function-statement.md)
- [Практическое руководство. Возврат значения из процедуры](./how-to-return-a-value-from-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
