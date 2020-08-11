---
title: Запросы в LINQ to DataSet
description: Сведения о составлении запросов в LINQ to DataSet путем получения источника или источников данных, создания запроса и выполнения запроса.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
ms.openlocfilehash: eee04959493914018904b61b0e5a289f172f2f18
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063722"
---
# <a name="queries-in-linq-to-dataset"></a>Запросы в LINQ to DataSet
Запрос представляет собой выражение, извлекающее данные из источника данных. Запросы обычно выражаются на специализированном языке запросов, например SQL для реляционных баз данных и XQuery для XML. Поэтому разработчикам приходится учить новый язык запросов для каждого типа источника данных и формата данных, для которых выполняется запрос. Интегрированный в язык запрос (LINQ) предлагает упрощенную согласованную модель работы с данными для различных типов источников данных и различных форматов данных. Запросы LINQ всегда работают с программируемыми объектами.  
  
 Операция запроса LINQ состоит из трех действий: получение одного или нескольких источников данных, создание запроса и его выполнение.  
  
 Источники данных, реализующие <xref:System.Collections.Generic.IEnumerable%601> универсальный интерфейс, можно запрашивать через LINQ. Вызов метода <xref:System.Data.DataTableExtensions.AsEnumerable%2A> для <xref:System.Data.DataTable> возвращает объект, реализующий универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс, который служит источником данных для запросов LINQ to DataSet.  
  
 В запросе указываются данные, которые необходимо получить из источника данных. В запросе можно также указать, как следует сортировать, группировать и формировать возвращаемую информацию. В LINQ запрос хранится в переменной. Если запрос должен возвращать последовательность значений, переменная запроса должна иметь перечислимый тип данных. Эта переменная запроса не выполняет никаких действий и не возвращает данные. Она только хранит информацию о запросе. После создания запроса его необходимо выполнить, чтобы получить данные.  
  
 В запросе, возвращающем последовательность значений, переменная запроса никогда не содержит результаты запроса, а только хранит его команды. Выполнение запроса откладывается, пока переменная запроса используется в циклах `foreach` или `For Each`. Это называется *отложенным выполнением*; Это значит, что выполнение запроса происходит через некоторое время после создания запроса. Это означает, что запрос можно выполнять настолько часто, насколько это необходимо. Такое свойство полезно, например, если имеется база данных, которая обновляется другими приложениями. В собственном приложении можно создать запрос, который регулярно выполняется, каждый раз получая последние обновленные данные.  
  
 В отличие от отложенных запросов, возвращающих последовательности значений, запросы, получающие одноэлементное значение, выполняются немедленно. Примерами одноэлементных запросов являются <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> и <xref:System.Linq.Enumerable.First%2A>. Они выполняются немедленно, так как результаты запросов необходимы для вычисления одноэлементного результата. Например, чтобы вычислить среднее из результатов запросов, запросы должны быть выполнены, только тогда усредняющая функция получит данные для обработки. Для принудительного немедленного выполнения запроса, не создающего одноэлементное значение, можно также использовать метод <xref:System.Linq.Enumerable.ToList%2A> или <xref:System.Linq.Enumerable.ToArray%2A>. Такая методика принудительного немедленного выполнения может оказаться полезной при кэшировании результатов запроса.
  
## <a name="queries"></a>Запросы  
 LINQ to DataSet запросы можно сформулировать двумя различными синтаксисами: синтаксис выражений запроса и синтаксис запросов на основе методов.  
  
### <a name="query-expression-syntax"></a>Синтаксис выражений запросов  
 Выражения запроса используют декларативный синтаксис запроса. Этот синтаксис позволяет разработчику писать запросы на C# или Visual Basic в формате, похожем на SQL. С помощью синтаксиса выражения запроса можно выполнять даже сложную фильтрацию, упорядочение и группирование операций в источнике данных с помощью минимального программного кода. Дополнительные сведения см. в разделе [выражения запросов LINQ](../../../csharp/linq/index.md#query-expression-overview) и [основные операции запросов (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).
  
 .NET Framework среде CLR не удается считать сам синтаксис выражения запроса. Таким образом, во время компиляции выражения запроса преобразуются в то, что понятно CLR - вызовы методов. Эти методы называются *стандартными операторами запросов*. Разработчик может вызывать их напрямую, используя синтаксис методов вместо синтаксиса запроса. Дополнительные сведения см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md). Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запросов](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 В следующем примере показано использование метода <xref:System.Linq.Enumerable.Select%2A> для выборки всех строк из таблицы `Product` и отображения названий продуктов.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="method-based-query-syntax"></a>Синтаксис запросов, основанных на методе  
 Другой способ формулировки LINQ to DataSet запросов — использование запросов на основе методов. Он представляет собой последовательность непосредственных вызовов методов операторов LINQ, передающих лямбда-выражения в качестве параметров. Дополнительные сведения см. в разделе [Лямбда-выражения](../../../csharp/language-reference/operators/lambda-expressions.md).  
  
 В следующем примере выражение <xref:System.Linq.Enumerable.Select%2A> используется для возврата всех строк из таблицы `Product` и вывода названий продуктов.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="composing-queries"></a>Создание запросов  
 Как указывалось выше в этом разделе, переменная запроса хранит команды запроса, если он предназначен для возврата последовательности значений. Если запрос не содержит метод, приводящий к немедленному выполнению запроса, фактическое выполнение запроса откладывается до завершения обработки переменной запроса в цикле `foreach` или `For Each`. Отложенное выполнение позволяет объединять несколько запросов или расширять один запрос. При расширении запроса он изменяется, включая в себя новые операции, а последующее выполнение отразит эти изменения. В следующем примере первый запрос возвращает все продукты. Второй запрос расширяет первый, используя предложение `Where`, чтобы возвратить все продукты с размером «L»:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 После выполнения запроса нельзя создавать дополнительные запросы, а все последующие запросы будут использовать операторы LINQ из кэша памяти. Выполнение запроса произойдет при переборе переменной запроса в `foreach` `For Each` операторе или или при вызове одного из операторов преобразования LINQ, которые приводят к немедленному выполнению. В число этих операторов входят следующие: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> и <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
 В следующем примере первый запрос возвращает все продукты, отсортированные по списочной цене. Метод <xref:System.Linq.Enumerable.ToArray%2A> используется для принудительного немедленного выполнения запроса:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## <a name="see-also"></a>См. также раздел

- [Руководство по программированию](programming-guide-linq-to-dataset.md)
- [Запросы к DataSet](querying-datasets-linq-to-dataset.md)
- [Приступая к работе с LINQ в C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [Приступая к работе с LINQ в Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
