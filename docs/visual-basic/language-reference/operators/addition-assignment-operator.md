---
description: 'Дополнительные сведения о operator: + = (Visual Basic)'
title: Оператор +=
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: e5a6b8fcc75e44c00ee18fec9cd57e68b1218de7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640476"
---
# <a name="-operator-visual-basic"></a>Оператор += (Visual Basic)

Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству. Также можно использовать для сцепления `String` выражения с `String` переменной или свойством и назначения результата переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Компоненты  

 `variableorproperty`  
 Обязательный элемент. Любое числовое `String` значение, переменная или свойство.  
  
 `expression`  
 Обязательный элемент. Любое числовое `String` выражение или.  
  
## <a name="remarks"></a>Remarks  

 Элемент в левой части `+=` оператора может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).  
  
 `+=`Оператор добавляет значение справа к переменной или свойству слева и присваивает результат переменной или свойству слева. `+=`Оператор также можно использовать для сцепления `String` выражения непосредственно с `String` переменной или свойством слева и присвоить результат переменной или свойству слева.  
  
> [!NOTE]
> При использовании `+=` оператора может быть невозможно определить, будет ли выполняться сложение или объединение строк. Используйте `&=` оператор для объединения, чтобы исключить неоднозначность и предоставить код для самостоятельного документирования.  
  
 Этот оператор присваивания неявно выполняет расширяющие, но не сужающие преобразования, если среда компиляции применяет строгую семантику. Дополнительные сведения об этих преобразованиях см. в разделе [расширяющие и сужающие преобразования](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Дополнительные сведения о семантике строгих и неразрешений см. в разделе [оператор Option строгий](../statements/option-strict-statement.md).  
  
 Если семантика разрешений разрешена, `+=` оператор неявно выполняет различные строковые и числовые преобразования, идентичные выполняемым `+` оператором. Дополнительные сведения об этих преобразованиях см. в разделе [оператор +](addition-operator.md).  
  
## <a name="overloading"></a>Перегрузка  

 `+`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Перегрузка `+` оператора влияет на поведение `+=` оператора. Если ваш код использует `+=` класс или структуру, перегрузки `+` , убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `+=` для объединения значения одной переменной с другой. Первая часть использует `+=` с числовыми переменными для добавления одного значения в другое. Во второй части используется `+=` с `String` переменными для сцепления одного значения с другим. В обоих случаях результат присваивается первой переменной.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 `num1`Теперь значение равно 13, а значение `str1` равно "103".  
  
## <a name="see-also"></a>См. также

- [Оператор +](addition-operator.md)
- [Операторы присваивания](assignment-operators.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Операторы объединения](concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы](../../programming-guide/language-features/statements.md)
