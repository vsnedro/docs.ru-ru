---
title: Выполнение запросов на основе состояния среды выполнения (Visual Basic)
description: Описывает различные методы, которые код может использовать для динамического запроса в зависимости от состояния среды выполнения, путем изменения либо вызовов методов LINQ, либо деревьев выражений, переданных в эти методы.
ms.date: 02/14/2021
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: c9f57950b2c26c0cca798ab632da90bf9f6c519a
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584853"
---
# <a name="querying-based-on-runtime-state-visual-basic"></a>Выполнение запросов на основе состояния среды выполнения (Visual Basic)

Рассмотрим код, который определяет <xref:System.Linq.IQueryable> или [IQueryable (Of T)](<xref:System.Linq.IQueryable%601>) для источника данных:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Initialize":::

Каждый раз при выполнении этого кода будет выполнен тот же точный запрос. Это часто не очень полезно, так как может потребоваться, чтобы код выполнял различные запросы в зависимости от условий во время выполнения. В этой статье описывается, как можно выполнить другой запрос на основе состояния среды выполнения.

## <a name="iqueryable--iqueryableof-t-and-expression-trees"></a>IQueryable и IQueryable (Of T) и деревья выражений

По сути, <xref:System.Linq.IQueryable> компонент имеет два компонента:

* <xref:System.Linq.IQueryable.Expression>&mdash;представление компонентов текущего запроса, зависящее от языка и источника данных, в виде дерева выражения.
* <xref:System.Linq.IQueryable.Provider>&mdash;экземпляр поставщика LINQ, который знает, как материализовать текущий запрос в значение или набор значений.

В контексте динамической запросов поставщик обычно остается неизменным. дерево выражения запроса будет отличаться от запроса к запросу.

Деревья выражений являются неизменяемыми; Если требуется другое дерево выражения и, &mdash; таким же, другой запрос &mdash; , необходимо перевести существующее дерево выражения в новое, а значит новое <xref:System.Linq.IQueryable> .

В следующих разделах описываются конкретные методы запроса по-разному в ответ на состояние среды выполнения.

- Использовать состояние среды выполнения из дерева выражений
- Вызов дополнительных методов LINQ
- Изменение дерева выражения, переданного в методы LINQ
- Создайте дерево выражения [Expression (из тделегате)](xref:System.Linq.Expressions.Expression%601) с помощью методов фабрики <xref:System.Linq.Expressions.Expression>
- Добавление узлов вызова метода в <xref:System.Linq.IQueryable> дерево выражения
- Создание строк и использование [динамической библиотеки LINQ](https://dynamic-linq.net/)

## <a name="use-runtime-state-from-within-the-expression-tree"></a>Использовать состояние среды выполнения из дерева выражений

При условии, что поставщик LINQ поддерживает его, самый простой способ динамического запроса заключается в ссылке на состояние среды выполнения непосредственно в запросе через закрытую переменную, как `length` в следующем примере кода:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Runtime_state_from_within_expression_tree":::

Внутреннее дерево выражения &mdash; и, таким образом, запрос &mdash; не был изменен; запрос возвращает разные значения, так как значение `length` было изменено.

## <a name="call-additional-linq-methods"></a>Вызов дополнительных методов LINQ

Как правило, [встроенные методы LINQ](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) выполняются в <xref:System.Linq.Queryable> два этапа:

* Заключите текущее дерево выражения в оболочку, <xref:System.Linq.Expressions.MethodCallExpression> представляющую вызов метода.
* Передайте инкапсулированное дерево выражения обратно в поставщик, чтобы вернуть значение через <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> метод поставщика или вернуть объект переведенного запроса через <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> метод.

Чтобы получить новый запрос, можно заменить исходный запрос результатом метода [IQueryable (Of T)](xref:System.Linq.IQueryable%601), возвращающего значение. Это условие можно выполнять в зависимости от состояния среды выполнения, как показано в следующем примере:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a>Изменение дерева выражения, переданного в методы LINQ

К методам LINQ можно передать разные выражения в зависимости от состояния среды выполнения:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Varying_expressions":::

Также может потребоваться составить различные подвыражения, используя сторонние библиотеки, например [Линккит](http://www.albahari.com/nutshell/linqkit.aspx) [предикатебуилдер](http://www.albahari.com/nutshell/predicatebuilder.aspx):

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compose_expression":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a>Создание деревьев выражений и запросов с помощью методов фабрики

Во всех примерах мы определили тип элемента во время компиляции и, таким же, &mdash; `String` &mdash; тип запроса &mdash; `IQueryable(Of String)` . Может потребоваться добавить компоненты в запрос любого типа элемента или добавить различные компоненты в зависимости от типа элемента. Вы можете создавать деревья выражений с нуля с помощью методов фабрики <xref:System.Linq.Expressions.Expression?displayProperty=fullName> и, таким образом, адаптировать выражение во время выполнения к определенному типу элемента.

### <a name="constructing-an-expressionof-tdelegate"></a>Построение [выражения (Of тделегате)](xref:System.Linq.Expressions.Expression%601)

При создании выражения для передачи в один из методов LINQ фактически создается экземпляр [выражения (Of тделегате)](xref:System.Linq.Expressions.Expression%601), где `TDelegate` — это некоторый тип делегата, например `Func(Of String, Boolean)` , `Action` или пользовательский тип делегата.

[Выражение (Of тделегате))](xref:System.Linq.Expressions.Expression%601) наследует от <xref:System.Linq.Expressions.LambdaExpression> , который представляет полное лямбда-выражение следующего вида:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compiler_generated":::

<xref:System.Linq.Expressions.LambdaExpression>Компонент имеет два компонента:

* список параметров, &mdash; `(x As String)` &mdash; представленный <xref:System.Linq.Expressions.LambdaExpression.Parameters> свойством
* тело, &mdash; `x.StartsWith("a")` &mdash; представленное <xref:System.Linq.Expressions.LambdaExpression.Body> свойством.

Ниже приведены основные шаги создания [выражения (Of тделегате)](xref:System.Linq.Expressions.Expression%601) .

* Определите <xref:System.Linq.Expressions.ParameterExpression> объекты для каждого из параметров (если таковые имеются) в лямбда-выражении с помощью <xref:System.Linq.Expressions.Expression.Parameter%2A> метода Factory.

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_parameter":::

* Создайте текст <xref:System.Linq.Expressions.LambdaExpression> , используя <xref:System.Linq.Expressions.ParameterExpression> заданные вами (s), и фабричные методы в <xref:System.Linq.Expressions.Expression> . Например, выражение, представляющее, `x.StartsWith("a")` может быть построено следующим образом:

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_body":::

* Заключите параметры и текст в выражение с типом времени компиляции [(Of тделегате)](xref:System.Linq.Expressions.Expression%601), используя подходящую <xref:System.Linq.Expressions.Expression.Lambda%2A> перегрузку метода фабрики:

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_lambda":::

В следующих разделах описывается сценарий, в котором может потребоваться создать [выражение (Of тделегате)](xref:System.Linq.Expressions.Expression%601) для передачи в метод LINQ, а также полный пример того, как это сделать с помощью методов фабрики.

### <a name="scenario"></a>Сценарий

Допустим, у вас есть несколько типов сущностей:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Entities.vb":::

Для любого из этих типов сущностей необходимо отфильтровать и возвратить только те сущности, которые имеют заданный текст в одном из `string` полей. Для нужно `Person` выполнить поиск по `FirstName` `LastName` свойствам и:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="PersonsQry":::

но для нужно `Car` найти только `Model` свойство:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="CarsQry":::

Хотя можно написать одну пользовательскую функцию для `IQueryable(Of Person)` и другую для `IQueryable(Of Car)` , следующая функция добавляет эту фильтрацию к любому существующему запросу независимо от конкретного типа элемента.

### <a name="example"></a>Пример

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate":::

Поскольку `TextFilter` функция принимает и возвращает [IQueryable (Of T)](xref:System.Linq.IQueryable%601) (а не только <xref:System.Linq.IQueryable> ), после текстового фильтра можно добавить дополнительные элементы запроса, написанные во время компиляции.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="add-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a>Добавление узлов вызова метода в <xref:System.Linq.IQueryable> дерево выражения

Если у вас есть <xref:System.Linq.IQueryable> вместо [IQueryable (Of T)](xref:System.Linq.IQueryable%601), вы не можете напрямую вызывать универсальные методы LINQ. В качестве альтернативы можно создать внутреннее дерево выражения, как показано выше, и использовать отражение для вызова соответствующего метода LINQ при передаче в дерево выражения.

Можно также дублировать функциональность метода LINQ, заключив все дерево в, <xref:System.Linq.Expressions.MethodCallExpression> которое представляет вызов метода LINQ:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_lambdaexpression":::

Обратите внимание, что в этом случае нет `T` универсального заполнителя времени компиляции, поэтому вы будете использовать <xref:System.Linq.Expressions.Expression.Lambda%2A> перегрузку, для которой не требуются сведения о типе времени компиляции, и что создает <xref:System.Linq.Expressions.LambdaExpression> вместо [выражения (Of тделегате)](xref:System.Linq.Expressions.Expression%601).

## <a name="the-dynamic-linq-library"></a>Динамическая библиотека LINQ

Построение деревьев выражений с помощью фабричных методов относительно сложно; проще создавать строки. [Динамическая библиотека LINQ](https://dynamic-linq.net/) предоставляет набор методов расширения <xref:System.Linq.IQueryable> , соответствующих стандартным методам LINQ в <xref:System.Linq.Queryable> , и который принимает строки в [специальном синтаксисе](https://dynamic-linq.net/expression-language) вместо деревьев выражений. Библиотека создает соответствующее дерево выражения из строки и может возвращать полученный преобразованный результат <xref:System.Linq.IQueryable> .

Например, предыдущий пример (включая построение дерева выражения) может быть переписан следующим образом:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Dynamic_linq":::

## <a name="see-also"></a>См. также

- [Expression Trees (Visual Basic)](index.md) (Деревья выражений (Visual Basic))
- [Практическое руководство. Выполнение деревьев выражений (Visual Basic)](how-to-execute-expression-trees.md)
