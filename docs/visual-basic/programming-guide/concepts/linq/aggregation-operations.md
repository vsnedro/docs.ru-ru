---
title: Операции агрегирования
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 1cf82d8acfdb1f8b0fc33c324064574b0dd01f4a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078402"
---
# <a name="aggregation-operations-visual-basic"></a>Операции агрегирования (Visual Basic)

Статистическая операция вычисляет одно значение по коллекции значений. Например, статистической обработкой является вычисление средней дневной температуры с использованием значений дневной температуры за месяц.  
  
 На приведенном ниже рисунке показаны результаты двух различных операций агрегирования с последовательностью чисел. Первая операция суммирует числа. Вторая операция возвращает максимальное значение в последовательности.  
  
 ![Рисунок, показывающий операции агрегирования LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции агрегирования.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Статистическое выражение|Выполняет пользовательскую операцию агрегирования со значениями коллекции.|Не применяется|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Метод Average|Вычисляет среднее значение коллекции значений.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Count|Подсчитывает число элементов в коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Подсчитывает число элементов в большой коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Максимум|Определяет максимальное значение в коллекции.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Минимум|Определяет минимальное значение в коллекции.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Вычисляет сумму значений в коллекции.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
  
### <a name="average"></a>Среднее значение  

 В следующем примере кода используется `Aggregate Into Average` предложение в Visual Basic для вычисления средней температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Count  

 В следующем примере кода используется `Aggregate Into Count` предложение в Visual Basic для подсчета количества значений в массиве, которые больше или равны 80.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  

 В следующем примере кода предложение используется `Aggregate Into LongCount` для подсчета количества значений в массиве.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Макс.  

 В следующем примере кода предложение используется `Aggregate Into Max` для вычисления максимальной температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Min  

 В следующем примере кода предложение используется `Aggregate Into Min` для вычисления минимальной температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>SUM  

 В следующем примере кода предложение используется `Aggregate Into Sum` для вычисления общей суммы расходов из массива значений, представляющих расходы.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](standard-query-operators-overview.md)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [Руководство. Вычисление значений столбцов в текстовом файле CSV (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [How to: Count, Sum, or Average Data](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)
- [How to: Find the Minimum or Maximum Value in a Query Result](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)
- [Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (Visual Basic)](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Как запросить общее число байтов в наборе папок (LINQ) (Visual Basic)](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
