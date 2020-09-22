---
title: Оператор ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: a956ffdaa3456ed09443f25c3383b6aab52fb5bf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867067"
---
# <a name="-operator-visual-basic"></a>Оператор ^= (Visual Basic)

Возвращает значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Компоненты  

 `variableorproperty`  
 Обязательный элемент. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Remarks  

 Элемент в левой части `^=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).  
  
 `^=`Оператор сначала выдает значение переменной или свойства (в левой части оператора) в степень значения выражения (в правой части оператора) (справа). Затем оператор присваивает результат этой операции с переменной или свойством.  
  
 Visual Basic всегда выполняет возведение в степень в [типе данных Double](../data-types/double-data-type.md). Операнды любого другого типа преобразуются в `Double` , а результат всегда равен `Double` .  
  
 Значение `expression` может быть дробным, отрицательным или обоими.  
  
## <a name="overloading"></a>Перегрузка  

 [Оператор ^](exponentiation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка `^` оператора влияет на поведение `^=` оператора. Если ваш код использует `^=` класс или структуру, перегрузки `^` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `^=` для возведения значения одной `Integer` переменной в степень второй переменной и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>См. также

- [Оператор ^](exponentiation-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
