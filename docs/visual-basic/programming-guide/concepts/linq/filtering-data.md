---
description: 'Дополнительные сведения: Фильтрация данных (Visual Basic)'
title: Фильтрация данных
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 2e259209df35a89eb4730f79ffccfee7cb64b9e9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428601"
---
# <a name="filtering-data-visual-basic"></a>Фильтрация данных (Visual Basic)

Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию. Это также называется выборкой.

На следующем рисунке показаны результаты операции фильтрации последовательности символов. Предикат для операции фильтрации указывает, что символ должен быть "A".

![Схема, иллюстрирующая операцию фильтрации LINQ](./media/filtering-data/linq-filter-operation.png)

Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.

## <a name="methods"></a>Методы

|Имя метода|Описание|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|
|-----------------|-----------------|------------------------------------------|----------------------|
|OfType|Выбирает значения в зависимости от возможности приведения их к указанному типу.|Не применяется|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|Where|Выбирает значения, основанные на функции предиката.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса

В следующем примере используется `Where` для фильтрации из массива строк, имеющих определенную длину.

```vb
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}

Dim query = From word In words
            Where word.Length = 3
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](standard-query-operators-overview.md)
- [Предложение WHERE](../../../language-reference/queries/where-clause.md)
- [How to: Filter Query Results](../../language-features/linq/how-to-filter-query-results-by-using-linq.md) (Практическое руководство. Фильтрование результатов запроса)
- [Как запрашивать метаданные сборки с помощью отражения (LINQ) (Visual Basic)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Как запросить файлы с указанным атрибутом или именем (Visual Basic)](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
