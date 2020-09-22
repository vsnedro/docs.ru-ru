---
title: Оператор /=
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: d47a69e454305ce9417a46b5bbfbbb55a1ad1dc3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867079"
---
# <a name="-operator-visual-basic"></a>Оператор /= (Visual Basic)

Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Компоненты  

 `variableorproperty`  
 Обязательный элемент. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Remarks  

 Элемент в левой части `/=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).  
  
 `/=`Оператор сначала делит значение переменной или свойства (в левой части оператора) на значение выражения (в правой части оператора). в противном случае. Затем оператор присваивает результат операции с плавающей запятой переменной или свойству.  
  
 Эта инструкция присваивает `Double` значение переменной или свойству слева. Если `Option Strict` имеет значение `On` , `variableorproperty` должно быть `Double` . Если `Option Strict` параметр имеет значение `Off` , Visual Basic выполняет неявное преобразование и присваивает результирующее значение `variableorproperty` с возможной ошибкой во время выполнения. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Option](../statements/option-strict-statement.md)parallelism.  
  
## <a name="overloading"></a>Перегрузка  

 [Оператор/(Visual Basic)](floating-point-division-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Перегрузка `/` оператора влияет на поведение `/=` оператора. Если ваш код использует `/=` класс или структуру, перегрузки `/` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `/=` для разделения одной `Integer` переменной на вторую и присваивания значения частного для первой переменной.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор/(Visual Basic)](floating-point-division-operator.md)
- [\\Оператор =](integer-division-assignment-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
