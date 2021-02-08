---
description: 'Дополнительные сведения: оператор OrElse (Visual Basic)'
title: Оператор OrElse
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 48ccbda1e0cb4f655b28e902b22fbfe0c3e66ac8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795330"
---
# <a name="orelse-operator-visual-basic"></a>Оператор OrElse (Visual Basic)

Выполняет сокращенное вычисление инклюзивного логического сложения двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Компоненты  

 `result`  
 Обязательный. Произвольное выражение `Boolean` .  
  
 `expression1`  
 Обязательный. Произвольное выражение `Boolean` .  
  
 `expression2`  
 Обязательный. Произвольное выражение `Boolean` .  
  
## <a name="remarks"></a>Remarks  

 Логическая операция называется *сокращенной* , если скомпилированный код может обходить вычисление одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет окончательный результат операции, нет необходимости оценивать второе выражение, так как оно не может изменить окончательный результат. Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или если оно включает вызовы процедур.  
  
 Если одно или оба выражения имеют значение `True` , `result` то имеет значение `True` . В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` имеет значение |И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(не вычислено)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Типы данных  

 `OrElse`Оператор определен только для [типа данных Boolean](../data-types/boolean-data-type.md). При необходимости Visual Basic преобразует каждый операнд в `Boolean` перед вычислением выражения. Если результат присваивается числовому типу, Visual Basic преобразует его в `Boolean` этот тип, который `False` станет `0` и `True` станет `-1` .
Дополнительные сведения см. в разделе [преобразования логических типов](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Перегрузка  

 [Оператор OR](or-operator.md) и [оператор IsTrue](istrue-operator.md) могут быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры. Перегрузка `Or` `IsTrue` операторов и влияет на поведение `OrElse` оператора. Если код использует `OrElse` класс или структуру, перегрузку `Or` и `IsTrue` , убедитесь, что вы понимаете их переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `OrElse` для выполнения логического сложения двух выражений. Результатом является `Boolean` значение, которое показывает, имеет ли одно из двух выражений значение true. Если первое выражение равно `True` , второе не вычисляется.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 В предыдущем примере создаются результаты `True` , `True` и `False` соответственно. В вычислении `firstCheck` второе выражение не вычисляется, так как первый уже существует `True` . Однако второе выражение вычисляется в вычислении `secondCheck` .  
  
## <a name="example"></a>Пример  

 В следующем примере показан `If` оператор..., `Then` содержащий два вызова процедуры. Если первый вызов возвращает `True` , вторая процедура не вызывается. Это может привести к непредвиденным результатам, если вторая процедура выполняет важные задачи, которые всегда должны выполняться при выполнении этого раздела кода.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>См. также

- [Логические (побитовые) операторы (Visual Basic)](logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Оператор Or](or-operator.md)
- [Оператор IsTrue](istrue-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
