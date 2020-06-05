---
title: '&amp;Оператор ='
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371990"
---
# <a name="amp-operator-visual-basic"></a>&amp;Оператор = (Visual Basic)
Сцепляет `String` выражение с `String` переменной или свойством и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Компоненты  
 `variableorproperty`  
 Обязательный. Любая `String` переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное выражение `String` .  
  
## <a name="remarks"></a>Комментарии  
 Элемент в левой части `&=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md). `&=`Оператор объединяет `String` выражение непосредственно с `String` переменной или свойством слева, а затем присваивает результат переменной или свойству слева.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор&](concatenation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка `&` оператора влияет на поведение `&=` оператора. Если ваш код использует `&=` класс или структуру, перегрузки `&` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `&=` для сцепления двух `String` переменных и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [Оператор&](concatenation-operator.md)
- [Оператор + =](addition-assignment-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Операторы объединения](concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
