---
title: Оператор AndAlso
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 8b67897956a21d06d465cf206856354d2e3f9d68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371938"
---
# <a name="andalso-operator-visual-basic"></a>Оператор AndAlso (Visual Basic)
Выполняет сокращенное вычисление логического умножения двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`result`|Обязательный. Произвольное выражение `Boolean` . Результатом `Boolean` сравнения двух выражений является результат.|  
|`expression1`|Обязательный. Произвольное выражение `Boolean` .|  
|`expression2`|Обязательный. Произвольное выражение `Boolean` .|  
  
## <a name="remarks"></a>Комментарии  
 Логическая операция называется *сокращенной* , если скомпилированный код может обходить вычисление одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет окончательный результат операции, нет необходимости оценивать второе выражение, так как оно не может изменить окончательный результат. Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или если оно включает вызовы процедур.  
  
 Если оба выражения имеют значение `True` , `result` то имеет значение `True` . В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` имеет значение |И `expression2` является|Значение `result` равно|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(не вычислено)|`False`|  
  
## <a name="data-types"></a>Типы данных  
 `AndAlso`Оператор определен только для [типа данных Boolean](../data-types/boolean-data-type.md). При необходимости Visual Basic преобразует каждый операнд в `Boolean` перед вычислением выражения. Если результат присваивается числовому типу, Visual Basic преобразует его в `Boolean` этот тип, который `False` станет `0` и `True` станет `-1` .
Дополнительные сведения см. в разделе [преобразования логических типов](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Перегрузка  
 [Операторы and](and-operator.md) и [IsFalse](isfalse-operator.md) можно *перегружать*, что означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры. Перегрузка `And` `IsFalse` операторов и влияет на поведение `AndAlso` оператора. Если код использует `AndAlso` класс или структуру, перегрузку `And` и `IsFalse` , убедитесь, что вы понимаете их переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `AndAlso` для выполнения логического умножения двух выражений. Результат представляет собой `Boolean` значение, которое показывает, является ли выражение истинным. Если первое выражение равно `False` , второе не вычисляется.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 В предыдущем примере создаются результаты `True` , `False` и `False` соответственно. В вычислении `secondCheck` второе выражение не вычисляется, так как первый уже существует `False` . Однако второе выражение вычисляется в вычислении `thirdCheck` .  
  
## <a name="example"></a>Пример  
 В следующем примере показана `Function` процедура поиска заданного значения в элементах массива. Если массив пуст или если длина массива была превышена, `While` инструкция не проверяет элемент массива на соответствие значению поиска.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>См. также раздел

- [Логические (побитовые) операторы (Visual Basic)](logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Оператор And](and-operator.md)
- [Оператор IsFalse](isfalse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
