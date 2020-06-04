---
title: Сортировка данных
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: a5ccff745995ed7f41731cf98fb7c49d3247d994
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406798"
---
# <a name="sorting-data-visual-basic"></a>Сортировка данных (Visual Basic)

Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов. Первый критерий сортировки выполняет первичную сортировку элементов. Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.

На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов.

![Рисунок с операциями сортировки в алфавитном порядке.](./media/sorting-data/alphabetical-sort-operation.png)

Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.

## <a name="methods"></a>Методы

|Имя метода|Описание:|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|
|-----------------|-----------------|------------------------------------------|----------------------|
|OrderBy|Сортировка значений в возрастающем порядке.|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|OrderByDescending|Сортировка значений в убывающем порядке.|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|ThenBy|Дополнительная сортировка по возрастанию.|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|ThenByDescending|Дополнительная сортировка по убыванию.|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|Reverse|Изменение порядка элементов в коллекции на обратный.|Не применяется|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов

### <a name="primary-sort-examples"></a>Примеры основной сортировки

#### <a name="primary-ascending-sort"></a>Основная сортировка по возрастанию

В следующем примере показано использование предложения `Order By` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a>Основная сортировка по убыванию

В следующем примере показано использование предложения `Order By Descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a>Примеры дополнительной сортировки

#### <a name="secondary-ascending-sort"></a>Дополнительная сортировка по возрастанию

В следующем примере показано использование предложения `Order By` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве. Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a>Дополнительная сортировка по убыванию

В следующем примере показано использование предложения `Order By Descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию. Строки сортируются основным образом по длине и дополнительно — по первой букве строки.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](standard-query-operators-overview.md)
- [Предложение Order By](../../../language-reference/queries/order-by-clause.md)
- [How to: Sort Query Results](../../language-features/linq/how-to-sort-query-results-by-using-linq.md) (Практическое руководство. Сортировка результатов запроса)
- [Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
