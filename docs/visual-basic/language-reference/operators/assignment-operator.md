---
title: Оператор =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 516cb21e02d9fb2cd4b8d72282bb74163e1fb14b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371769"
---
# <a name="-operator-visual-basic"></a>Оператор = (Visual Basic)
Присваивает значение переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Компоненты  
 `variableorproperty`  
 Любая изменяемая переменная или любое свойство.  
  
 `value`  
 Любой литерал, константа или выражение.  
  
## <a name="remarks"></a>Комментарии  
 Элемент в левой части знака равенства ( `=` ) может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md). `=`Оператор присваивает значение справа переменной или свойству слева.  
  
> [!NOTE]
> `=`Оператор также используется в качестве оператора сравнения. Дополнительные сведения см. в разделе [Операторы сравнения](comparison-operators.md).  
  
## <a name="overloading"></a>Перегрузка  
 `=`Оператор может быть перегружен только как оператор реляционного сравнения, а не как оператор присваивания. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан оператор присваивания. Значение справа присваивается переменной слева.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также раздел

- [Оператор&=](and-assignment-operator.md)
- [Оператор * =](multiplication-assignment-operator.md)
- [Оператор + =](addition-assignment-operator.md)
- [Оператор-= (Visual Basic)](subtraction-assignment-operator.md)
- [Оператор /= (Visual Basic)](floating-point-division-assignment-operator.md)
- [\\Оператор =](integer-division-assignment-operator.md)
- [Оператор ^ =](exponentiation-assignment-operator.md)
- [Операторы](../../programming-guide/language-features/statements.md)
- [Операторы сравнения](comparison-operators.md)
- [Доступно](../modifiers/readonly.md)
- [Вывод локального типа](../../programming-guide/language-features/variables/local-type-inference.md)
