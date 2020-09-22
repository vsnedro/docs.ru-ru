---
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: be2e401c7931b2637c14a3ea3b742a2c09917939
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869991"
---
# <a name="aggregate-clause-visual-basic"></a>Предложение Aggregate (Visual Basic)

Применяет одну или несколько агрегатных функций к коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательный. Переменная, используемая для прохода по элементам коллекции.|  
|`type`|Необязательный элемент. Тип параметра `element`. Если тип не указан, тип `element` выводится из `collection` .|  
|`collection`|Обязательный элемент. Ссылается на коллекцию для обработки.|  
|`clause`|Необязательный элемент. Одно или несколько предложений запроса, например `Where` предложение, для уточнения результата запроса с целью применения предложения Aggregate или предложений к.|  
|`expressionList`|Обязательный элемент. Одно или несколько выражений с разделителями-запятыми, которые обозначают агрегатную функцию, применяемую к коллекции. Можно применить псевдоним к агрегатной функции, чтобы указать имя элемента для результата запроса. Если псевдоним не указан, используется имя агрегатной функции. Примеры см. в разделе агрегатные функции далее в этом разделе.|  
  
## <a name="remarks"></a>Remarks  

 `Aggregate`Предложение можно использовать для включения в запросы агрегатных функций. Агрегатные функции выполняют проверки и вычисления для набора значений и возвращают одно значение. Доступ к вычисленному значению можно получить с помощью члена типа результата запроса. Стандартные агрегатные функции, которые можно использовать, — это функции,,,,,, `All` `Any` `Average` `Count` `LongCount` `Max` `Min` и `Sum` . Эти функции знакомы разработчикам, знакомым со статистическими выражениями в SQL. Они описаны в следующем разделе этой статьи.  
  
 Результат агрегатной функции включается в результат запроса в виде поля типа результата запроса. Можно указать псевдоним для результата агрегатной функции, чтобы указать имя элемента типа результата запроса, который будет содержать статистическое значение. Если псевдоним не указан, используется имя агрегатной функции.  
  
 `Aggregate`Предложение может начинать запрос или включать его в запрос в качестве дополнительного предложения. Если `Aggregate` предложение начинает запрос, результатом является единственное значение, которое является результатом агрегатной функции, указанной в `Into` предложении. Если в предложении указано более одной агрегатной функции `Into` , запрос возвращает один тип с отдельным свойством для ссылки на результат каждой агрегатной функции в `Into` предложении. Если `Aggregate` предложение включено в запрос как дополнительное предложение, тип, возвращаемый в коллекции запросов, будет иметь отдельное свойство для ссылки на результат каждой агрегатной функции в `Into` предложении.  
  
## <a name="aggregate-functions"></a>Агрегатные функции

Ниже приведены стандартные агрегатные функции, которые можно использовать с `Aggregate` предложением.  
  
### <a name="all"></a>Все

Возвращает значение, `true` Если все элементы в коллекции соответствуют заданному условию. в противном случае возвращает `false` . Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Любой

Возвращает значение, `true` Если любой элемент в коллекции удовлетворяет заданному условию; в противном случае возвращает `false` . Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Среднее значение

Вычисляет среднее значение всех элементов в коллекции или вычисляет заданное выражение для всех элементов в коллекции. Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Count

Подсчитывает количество элементов в коллекции. Можно указать необязательное `Boolean` выражение, чтобы подсчитать только количество элементов в коллекции, удовлетворяющее условию. Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Group

Относится к результатам запроса, сгруппированным в результате `Group By` `Group Join` предложения OR. `Group`Функция допустима только в `Into` предложении `Group By` `Group Join` предложения OR. Дополнительные сведения и примеры см. в разделе предложение [Group By](group-by-clause.md) и [предложение Group Join](group-join-clause.md).

### <a name="longcount"></a>LongCount

Подсчитывает количество элементов в коллекции. Можно указать необязательное `Boolean` выражение, чтобы подсчитать только количество элементов в коллекции, удовлетворяющее условию. Возвращает результат в виде `Long` . Пример см. в разделе `Count` агрегатная функция.

### <a name="max"></a>Макс.

Вычисление максимального значения из коллекции или вычисление заданного выражения для всех элементов в коллекции. Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Вычисление минимального значения из коллекции или вычисление заданного выражения для всех элементов в коллекции. Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>SUM

Вычисляет сумму всех элементов в коллекции или вычисляет заданное выражение для всех элементов в коллекции. Ниже приведен пример:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Пример  

В следующем примере показано, как использовать `Aggregate` предложение для применения агрегатных функций к результату запроса.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Создание определяемых пользователем агрегатных функций

 Можно включить собственные пользовательские агрегатные функции в выражение запроса, добавив методы расширения в <xref:System.Collections.Generic.IEnumerable%601> тип. Пользовательский метод может затем выполнить вычисление или операцию над перечислимой коллекцией, на которую ссылается агрегатная функция. Дополнительные сведения о методах расширения см. в разделе [Методы расширения](../../programming-guide/language-features/procedures/extension-methods.md).  
  
 Например, в следующем примере показана пользовательская агрегатная функция, которая вычисляет медианное значение коллекции чисел. Существует две перегрузки `Median` метода расширения. Первая перегрузка принимает в качестве входных данных коллекцию типа `IEnumerable(Of Double)` . Если `Median` для поля запроса типа вызывается агрегатная функция `Double` , этот метод будет вызван. Второй перегруженный `Median` метод может передаваться любым универсальным типом. Универсальная перегрузка `Median` метода принимает второй параметр, который ссылается на `Func(Of T, Double)` лямбда-выражение, чтобы проецировать значение для типа (из коллекции) в качестве соответствующего значения типа `Double` . Затем оно делегирует вычисление значения медианы другой перегрузке `Median` метода. Дополнительные сведения о лямбда-выражениях см. в разделе [лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 В следующем примере показаны образцы запросов, которые вызывают `Median` агрегатную функцию для коллекции типа `Integer` , и коллекцию типа `Double` . Запрос, вызывающий `Median` агрегатную функцию в коллекции типа, `Double` вызывает перегрузку `Median` метода, принимающего в качестве входных данных коллекцию типа `Double` . Запрос, вызывающий `Median` агрегатную функцию для коллекции типа `Integer` , вызывает универсальную перегрузку `Median` метода.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение WHERE](where-clause.md)
- [Предложение Group By](group-by-clause.md)
