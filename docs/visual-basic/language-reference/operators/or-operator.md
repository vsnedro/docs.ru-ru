---
title: Оператор Or
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 657b2a473b23789a8ba25fbd11c6b83538fa7803
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401424"
---
# <a name="or-operator-visual-basic"></a>Оператор Or (Visual Basic)
Выполняет логическое сложение двух `Boolean` выражений или побитовое сложение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Компоненты  
 `result`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа. Для `Boolean` сравнения `result` — это включающее логическое сложение двух `Boolean` значений. Для битовых операций `result` — это числовое значение, представляющее включающее побитовое сложение двух числовых битов.  
  
 `expression1`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа.  
  
 `expression2`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа.  
  
## <a name="remarks"></a>Комментарии  
 Для `Boolean` сравнения `result` параметр имеет значение, `False` только если оба `expression1` `expression2` значения и имеют значение `False` . В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` имеет значение |И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> В `Boolean` сравнении `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор OrElse](orelse-operator.md) выполняет *сокращенное вычисление*, означающее, что если `expression1` имеет значение `True` , то `expression2` не вычисляется.  
  
 Для побитовых операций `Or` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression1` имеет значение|И bit в `expression2` имеет|Бит в `result` имеет значение|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражения и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (– 1 для `True` и 0 для `False` ) и выполняет побитовую операцию.  
  
 Для `Boolean` сравнения тип данных результата — `Boolean` . Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2` . См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 `Or`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Or` для выполнения включающего логического сложения двух выражений. Результатом является `Boolean` значение, которое представляет, является ли одно из двух выражений `True` .  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 В предыдущем примере создаются результаты `True` , `True` и `False` соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Or` для выполнения инклюзивного логического сложения по отдельным битам двух числовых выражений. Бит в результирующем шаблоне задается, если один из соответствующих битов операндов имеет значение 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 В предыдущем примере выдается результат 10, 14 и 14 соответственно.  
  
## <a name="see-also"></a>См. также раздел

- [Логические (побитовые) операторы (Visual Basic)](logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Оператор OrElse](orelse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
