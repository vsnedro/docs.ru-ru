---
title: Оператор <<=
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: ff7cbb02a9a10dbe11450491e93fd85fd77b44ba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370665"
---
# <a name="-operator-visual-basic"></a>\<\<Оператор = (Visual Basic)
Выполняет арифметическое смещение влево для значения переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Компоненты  
 `variableorproperty`  
 Обязательный. Переменная или свойство целочисленного типа ( `SByte` ,, `Byte` , `Short` , `UShort` `Integer` , `UInteger` , `Long` или `ULong` ).  
  
 `amount`  
 Обязательный. Числовое выражение типа данных, которое расширяется до `Integer` .  
  
## <a name="remarks"></a>Комментарии  
 Элемент в левой части `<<=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).  
  
 `<<=`Оператор сначала выполняет арифметический сдвиг влево для значения переменной или свойства. Затем оператор присваивает результат этой операции с переменной или свойством.  
  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. При выполнении арифметического сдвига влево биты, сдвинутые за пределы диапазона результирующего типа данных, отбрасываются, а позиции битов, освобожденные справа, устанавливаются в ноль.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор<< ](left-shift-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка `<<` оператора влияет на поведение `<<=` оператора. Если ваш код использует `<<=` класс или структуру, перегрузки `<<` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `<<=` для сдвига битового шаблона `Integer` переменной влево на указанное значение и присваивает результат переменной.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>См. также раздел

- [Оператор<< ](left-shift-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Операторы сдвига битов](bit-shift-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
