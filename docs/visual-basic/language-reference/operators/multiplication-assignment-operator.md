---
title: Оператор *=
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: b06ebcb4f4100a0621f52a769543c0fb24fbb4bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401502"
---
# <a name="-operator-visual-basic"></a>Оператор *= (Visual Basic)
Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Компоненты  
 `variableorproperty`  
 Обязательный. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Комментарии  
 Элемент в левой части `*=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).  
  
 `*=`Оператор вначале умножает значение выражения (в правой части оператора) на значение переменной или свойства (в левой части оператора) (слева). Затем оператор присваивает результат этой операции переменной или свойству.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор *](multiplication-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка `*` оператора влияет на поведение `*=` оператора. Если ваш код использует `*=` класс или структуру, перегрузки `*` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `*=` для умножения одной `Integer` переменной на вторую и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>См. также раздел

- [* Оператор](multiplication-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
