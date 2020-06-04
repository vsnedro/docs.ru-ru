---
title: '>>Оператор ='
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: c3afe2bcc4b9732b5afd34df1b83eaebe707b3f5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409300"
---
# <a name="-operator-visual-basic"></a>Оператор >>= (Visual Basic)
Выполняет арифметическое смещение вправо для значения переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Компоненты  
 `variableorproperty`  
 Обязательный. Переменная или свойство целочисленного типа ( `SByte` ,, `Byte` , `Short` , `UShort` `Integer` , `UInteger` , `Long` или `ULong` ).  
  
 `amount`  
 Обязательный. Числовое выражение типа данных, которое расширяется до `Integer` .  
  
## <a name="remarks"></a>Комментарии  
 Элемент в левой части `>>=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).  
  
 `>>=`Оператор сначала выполняет арифметический сдвиг значения переменной или свойства вправо. Затем оператор присваивает результат этой операции с переменной или свойством.  
  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. При арифметическом сдвиге вправо биты, сдвинутые за пределы крайней правой позиции, отбрасываются, а крайний левый бит передается в позиции, освобожденные слева. Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые позиции устанавливаются в единицу. Если `variableorproperty` имеет положительное значение или тип данных имеет тип без знака, освобождаемые позиции устанавливаются в ноль.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор>> ](right-shift-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка `>>` оператора влияет на поведение `>>=` оператора. Если ваш код использует `>>=` класс или структуру, перегрузки `>>` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `>>=` для сдвига битового шаблона `Integer` переменной вправо на указанное значение и присваивает результат переменной.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>См. также раздел

- [Оператор>> ](right-shift-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Операторы сдвига битов](bit-shift-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
