---
description: 'Дополнительные сведения: примеры запросов Method-Based (LINQ to DataSet)'
title: Примеры запросов на основе методов (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
ms.openlocfilehash: 4597dee40bb3c75b6cbca946e0833672c8512c06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739174"
---
# <a name="method-based-query-examples-linq-to-dataset"></a>Примеры запросов на основе методов (LINQ to DataSet)

В этом разделе приводятся LINQ to DataSet примеры программирования в синтаксисе запросов на основе методов, которые используют стандартные операторы запросов. Объект, <xref:System.Data.DataSet> используемый в этих примерах, заполняется с помощью `FillDataSet` метода, который задается при [загрузке данных в набор данных](loading-data-into-a-dataset.md). Дополнительные сведения см. в разделе Общие сведения [о стандартных операторах запросов (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) или [Общие сведения о стандартных операторах запросов (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="in-this-section"></a>В этом разделе  

 [Проекция](method-based-query-syntax-examples-projection.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> для запроса к <xref:System.Data.DataSet>.  
  
 [Секционирование](method-based-query-syntax-examples-partitioning-linq.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Take%2A> для запроса <xref:System.Data.DataSet> и секционирования результатов.  
  
 [Упорядочение](method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> и <xref:System.Linq.Enumerable.ThenByDescending%2A> для запроса к <xref:System.Data.DataSet> и упорядочения результатов.  
  
 [Операторы набора](method-based-query-syntax-examples-set-operators.md)  
 В примерах этого раздела показано, как использовать операторы <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> и <xref:System.Linq.Enumerable.Union%2A> для сравнения на основе значений наборов и рядов данных.  
  
 [Операторы преобразования](method-based-query-syntax-examples-conversion-operators.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> и <xref:System.Linq.Enumerable.ToList%2A> для немедленного выполнения выражения запроса.  
  
 [Операторы элементов](method-based-query-syntax-examples-element-operators.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.First%2A> и <xref:System.Linq.Enumerable.ElementAt%2A> для получения элементов <xref:System.Data.DataRow> из <xref:System.Data.DataSet>.  
  
 [Операторы статистических выражений](method-based-query-syntax-examples-aggregate-operators.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запроса <xref:System.Data.DataSet> и статистической обработки данных.  
  
 [Присоединение](method-based-query-syntax-examples-join-linq-to-dataset.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.GroupJoin%2A> и <xref:System.Linq.Enumerable.Join%2A> для запроса к <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>См. также

- [Примеры выражений запросов](query-expression-examples-linq-to-dataset.md)
- [Связанные с определенными наборами данных примеры операторов](dataset-specific-operator-examples-linq-to-dataset.md)
- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
