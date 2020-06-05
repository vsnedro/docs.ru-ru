---
title: Оператор And
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: c2b135d27e14816c011a4f70793543aa835d960a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371951"
---
# <a name="and-operator-visual-basic"></a>Оператор And (Visual Basic)
Выполняет логическое умножение двух `Boolean` выражений или побитовое умножение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Компоненты  
 `result`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа. Для логического сравнения `result` — это логическое умножение двух `Boolean` значений. Для битовых операций `result` — это числовое значение, представляющее побитовое умножение двух числовых битов.  
  
 `expression1`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа.  
  
 `expression2`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа.  
  
## <a name="remarks"></a>Комментарии  
 Для логического сравнения `result` параметр имеет значение, `True` только если оба значения `expression1` и имеют значение `expression2` `True` . В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` имеет значение |И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> При логическом сравнении `And` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор AndAlso](andalso-operator.md) выполняет *сокращенное вычисление*, означающее, что если `expression1` имеет значение `False` , то `expression2` не вычисляется.  
  
 При применении к числовым значениям `And` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression1` имеет значение|И bit в `expression2` имеет|Бит в `result` имеет значение|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки для обеспечения точных результатов.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражения и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (– 1 для `True` и 0 для `False` ) и выполняет побитовую операцию.  
  
 Для логического сравнения тип данных результата — `Boolean` . Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2` . См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](data-types-of-operator-results.md).  
  
> [!NOTE]
> `And`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `And` для выполнения логического умножения двух выражений. Результатом является `Boolean` значение, которое показывает, равны ли оба выражения `True` .  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 В предыдущем примере создаются результаты `True` и `False` соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `And` для выполнения логического умножения отдельных битов двух числовых выражений. Бит в результирующем шаблоне задается, если для соответствующих битов в операндах задано значение 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 В предыдущем примере выдается результат 8, 2 и 0 соответственно.  
  
## <a name="see-also"></a>См. также раздел

- [Логические (побитовые) операторы (Visual Basic)](logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Оператор AndAlso](andalso-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
