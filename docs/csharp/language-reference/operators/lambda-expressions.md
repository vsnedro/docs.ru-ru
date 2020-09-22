---
title: Лямбда-выражения — Справочник по C#
description: Узнайте о лямбда-выражениях. Существуют лямбда-выражения, в которых в качестве тела используется выражение, а также лямбда-операторы, в которых в качестве тела используется блок операторов.
ms.date: 07/29/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 7f80c1a5d9136609935b25b5cce3792e80b9ac94
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536448"
---
# <a name="lambda-expressions-c-reference"></a><span data-ttu-id="eb4ff-104">Лямбда-выражения (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="eb4ff-104">Lambda expressions (C# reference)</span></span>

<span data-ttu-id="eb4ff-105">*Лямбда-выражение* является выражением любой из следующих двух форм:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-105">A *lambda expression* is an expression of any of the following two forms:</span></span>

- <span data-ttu-id="eb4ff-106">[Лямбда выражения](#expression-lambdas), имеющая выражение в качестве текста:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-106">[Expression lambda](#expression-lambdas) that has an expression as its body:</span></span>

  ```csharp
  (input-parameters) => expression
  ```

- <span data-ttu-id="eb4ff-107">[Лямбда оператора](#statement-lambdas), имеющая блок операторов в качестве текста:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-107">[Statement lambda](#statement-lambdas) that has a statement block as its body:</span></span>

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

<span data-ttu-id="eb4ff-108">Используйте [оператор объявления лямбда-выражения`=>`](lambda-operator.md) для отделения списка параметров лямбда-выражения от исполняемого кода.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-108">Use the [lambda declaration operator `=>`](lambda-operator.md) to separate the lambda's parameter list from its body.</span></span> <span data-ttu-id="eb4ff-109">Чтобы создать лямбда-выражение, необходимо указать входные параметры (если они есть) с левой стороны лямбда-оператора и блок выражений или операторов с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-109">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator and an expression or a statement block on the other side.</span></span>

<span data-ttu-id="eb4ff-110">Лямбда-выражение может быть преобразовано в тип [делегата](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-110">Any lambda expression can be converted to a [delegate](../builtin-types/reference-types.md#the-delegate-type) type.</span></span> <span data-ttu-id="eb4ff-111">Тип делегата, в который может быть преобразовано лямбда-выражение, определяется типами его параметров и возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-111">The delegate type to which a lambda expression can be converted is defined by the types of its parameters and return value.</span></span> <span data-ttu-id="eb4ff-112">Если лямбда-выражение не возвращает значение, оно может быть преобразовано в один из типов делегата `Action`; в противном случае его можно преобразовать в один из типов делегатов `Func`.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-112">If a lambda expression doesn't return a value, it can be converted to one of the `Action` delegate types; otherwise, it can be converted to one of the `Func` delegate types.</span></span> <span data-ttu-id="eb4ff-113">Например, лямбда-выражение, которое имеет два параметра и не возвращает значение, можно преобразовать в делегат <xref:System.Action%602>.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-113">For example, a lambda expression that has two parameters and returns no value can be converted to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="eb4ff-114">Лямбда-выражение, которое имеет два параметра и возвращает значение, можно преобразовать в делегат <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-114">A lambda expression that has one parameter and returns a value can be converted to a <xref:System.Func%602> delegate.</span></span> <span data-ttu-id="eb4ff-115">В следующем примере лямбда-выражение `x => x * x`, которое указывает параметр с именем `x` и возвращает значение `x` в квадрате, присваивается переменной типа делегата:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-115">In the following example, the lambda expression `x => x * x`, which specifies a parameter that's named `x` and returns the value of `x` squared, is assigned to a variable of a delegate type:</span></span>

[!code-csharp-interactive[lambda is delegate](snippets/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="eb4ff-116">Лямбда-выражения можно также преобразовать в типы [дерева выражения](../../programming-guide/concepts/expression-trees/index.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-116">Expression lambdas can also be converted to the [expression tree](../../programming-guide/concepts/expression-trees/index.md) types, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is expression tree](snippets/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="eb4ff-117">Лямбда-выражения можно использовать в любом коде, для которого требуются экземпляры типов делегатов или деревьев выражений, например в качестве аргумента метода <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> для передачи кода, который должен выполняться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-117">You can use lambda expressions in any code that requires instances of delegate types or expression trees, for example as an argument to the <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> method to pass the code that should be executed in the background.</span></span> <span data-ttu-id="eb4ff-118">Можно также использовать лямбда-выражения при применении [LINQ в C#](../../linq/index.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-118">You can also use lambda expressions when you write [LINQ in C#](../../linq/index.md), as the following example shows:</span></span>

[!code-csharp-interactive[lambda is argument in LINQ](snippets/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="eb4ff-119">При использовании синтаксиса на основе методов для вызова метода <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> в классе <xref:System.Linq.Enumerable?displayProperty=nameWithType> (например, в LINQ to Objects и LINQ to XML) параметром является тип делегата <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-119">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class, for example in LINQ to Objects and LINQ to XML, the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eb4ff-120">При вызове метода <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> в классе <xref:System.Linq.Queryable?displayProperty=nameWithType> (например, в LINQ to SQL) типом параметра является тип дерева выражения [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-120">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class, for example in LINQ to SQL, the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="eb4ff-121">В обоих случаях можно использовать одно и то же лямбда-выражение для указания значения параметра.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-121">In both cases you can use the same lambda expression to specify the parameter value.</span></span> <span data-ttu-id="eb4ff-122">Поэтому оба вызова `Select` выглядят одинаково, хотя на самом деле объект, созданный из лямбда-выражения, имеет другой тип.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-122">That makes the two `Select` calls to look similar although in fact the type of objects created from the lambdas is different.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="eb4ff-123">Выражения-лямбды</span><span class="sxs-lookup"><span data-stu-id="eb4ff-123">Expression lambdas</span></span>

<span data-ttu-id="eb4ff-124">Лямбда-выражение с выражением с правой стороны оператора `=>` называется *выражением лямбда*.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-124">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="eb4ff-125">Выражения-лямбды широко используются при конструировании [деревьев выражений](../../programming-guide/concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-125">Expression lambdas are used extensively in the construction of [expression trees](../../programming-guide/concepts/expression-trees/index.md).</span></span> <span data-ttu-id="eb4ff-126">Выражения-лямбды возвращают результат выражения и принимают следующую основную форму.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="eb4ff-127">Если лямбда-выражение имеет только один входной параметр, скобки можно не ставить; во всех остальных случаях они обязательны.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="eb4ff-128">Нулевое количество входных параметры задается пустыми скобками:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-128">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](snippets/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="eb4ff-129">Два и более входных параметра разделяются запятыми и заключаются в скобки:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-129">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](snippets/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="eb4ff-130">Иногда компилятору не удается определить входные типы.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-130">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="eb4ff-131">Вы можете указать типы данных в явном виде, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-131">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](snippets/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="eb4ff-132">Для входных параметров все типы нужно задать либо в явном, либо в неявном виде. В противном случае компилятор выдает ошибку [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-132">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="eb4ff-133">Текст выражения лямбды может состоять из вызова метода.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-133">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="eb4ff-134">Но при создании деревьев выражений, которые вычисляются вне контекста поддержки общеязыковой среды выполнения .NET, например в SQL Server, вызовы методов не следует использовать в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-134">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="eb4ff-135">Эти методы не имеют смысла вне контекста среды CLR .NET.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-135">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="eb4ff-136">Лямбды операторов</span><span class="sxs-lookup"><span data-stu-id="eb4ff-136">Statement lambdas</span></span>

<span data-ttu-id="eb4ff-137">Лямбда оператора напоминает выражение-лямбду, за исключением того, что оператор (или операторы) заключается в фигурные скобки:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-137">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

<span data-ttu-id="eb4ff-138">Тело лямбды оператора может состоять из любого количества операторов; однако на практике обычно используется не более двух-трех.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-138">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](snippets/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="eb4ff-139">Лямбды операторов нельзя использовать для создания деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-139">Statement lambdas cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="eb4ff-140">Асинхронные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="eb4ff-140">Async lambdas</span></span>

<span data-ttu-id="eb4ff-141">С помощью ключевых слов [async](../keywords/async.md) и [await](await.md) можно легко создавать лямбда-выражения и операторы, включающие асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-141">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../keywords/async.md) and [await](await.md) keywords.</span></span> <span data-ttu-id="eb4ff-142">Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-142">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="eb4ff-143">Такой же обработчик событий можно добавить с помощью асинхронного лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-143">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="eb4ff-144">Чтобы добавить этот обработчик, поставьте модификатор `async` перед списком параметров лямбда-выражения, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-144">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="eb4ff-145">Дополнительные сведения о создании и использовании асинхронных методов см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-145">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="eb4ff-146">Лямбда-выражения и кортежи</span><span class="sxs-lookup"><span data-stu-id="eb4ff-146">Lambda expressions and tuples</span></span>

<span data-ttu-id="eb4ff-147">В C# 7.0 представлена встроенная поддержка [кортежей](../builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-147">Starting with C# 7.0, the C# language provides built-in support for [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="eb4ff-148">Кортеж можно ввести в качестве аргумента лямбда-выражения, и лямбда-выражение также может возвращать кортеж.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-148">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="eb4ff-149">В некоторых случаях компилятор C# использует определение типа для определения типов компонентов кортежа.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-149">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="eb4ff-150">Кортеж определяется путем заключения в скобки списка его компонентов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-150">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="eb4ff-151">В следующем примере кортеж с тремя компонентами используется для передачи последовательности чисел в лямбда-выражение. Оно удваивает каждое значение и возвращает кортеж с тремя компонентами, содержащий результат операций умножения.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-151">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="eb4ff-152">Как правило, поля кортежи именуются как `Item1`, `Item2` и т. д. Тем не менее кортеж с именованными компонентами можно определить, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-152">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="eb4ff-153">Дополнительные сведения о кортежах в C# см. в статье [Типы кортежей](../../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-153">For more information about C# tuples, see [Tuple types](../../language-reference/builtin-types/value-tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="eb4ff-154">Лямбда-выражения со стандартными операторами запросов</span><span class="sxs-lookup"><span data-stu-id="eb4ff-154">Lambdas with the standard query operators</span></span>

<span data-ttu-id="eb4ff-155">В LINQ to Objects, наряду с другими реализациями, есть входной параметр, тип которого принадлежит к семейству универсальных делегатов <xref:System.Func%601>.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-155">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="eb4ff-156">Эти делегаты используют параметры типа для определения количества и типов входных параметров, а также тип возвращаемого значения делегата.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-156">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="eb4ff-157">Делегаты`Func` очень полезны для инкапсуляции пользовательских выражений, которые применяются к каждому элементу в наборе исходных данных.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-157">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="eb4ff-158">В качестве примера рассмотрим следующий тип делегата <xref:System.Func%602>:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-158">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="eb4ff-159">Экземпляр этого делегата можно создать как `Func<int, bool>`, где `int` — входной параметр, а `bool` — возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-159">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="eb4ff-160">Возвращаемое значение всегда указывается в последнем параметре типа.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-160">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="eb4ff-161">Например, `Func<int, string, bool>` определяет делегат с двумя входными параметрами, `int` и `string`, и типом возвращаемого значения `bool`.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-161">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="eb4ff-162">Следующий делегат `Func` при вызове возвращает логическое значение, которое показывает, равен ли входной параметр 5:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-162">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="eb4ff-163">Лямбда-выражения также можно использовать, когда аргумент имеет тип <xref:System.Linq.Expressions.Expression%601>, например в стандартных операторах запросов, которые определены в типе <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-163">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="eb4ff-164">При указании аргумента <xref:System.Linq.Expressions.Expression%601> лямбда-выражение компилируется в дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-164">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="eb4ff-165">В этом примере используется стандартный оператор запроса <xref:System.Linq.Enumerable.Count%2A>:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-165">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="eb4ff-166">Компилятор может вывести тип входного параметра ввода; но его также можно определить явным образом.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-166">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="eb4ff-167">Данное лямбда-выражение подсчитывает указанные целые значения (`n`), которые при делении на два дают остаток 1.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-167">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="eb4ff-168">В следующем примере кода показано, как создать последовательность, которая содержит все элементы массива `numbers`, предшествующие 9, так как это первое число последовательности, не удовлетворяющее условию:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-168">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="eb4ff-169">В следующем примере показано, как указать несколько входных параметров путем их заключения в скобки.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-169">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="eb4ff-170">Этот метод возвращает все элементы в массиве `numbers` до того числа, значение которого меньше его порядкового номера в массиве:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-170">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="eb4ff-171">Определение типа в лямбда-выражениях</span><span class="sxs-lookup"><span data-stu-id="eb4ff-171">Type inference in lambda expressions</span></span>

<span data-ttu-id="eb4ff-172">При написании лямбда-выражений обычно не требуется указывать тип входных параметров, так как компилятор может выводить этот тип на основе тела лямбда-выражения, типов параметров и других факторов, как описано в спецификации языка C#.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-172">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="eb4ff-173">Для большинства стандартных операторов запросов первой входное значение имеет тип элементов в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-173">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="eb4ff-174">При запросе `IEnumerable<Customer>` входная переменная считается объектом `Customer`, а это означает, что у вас есть доступ к его методам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-174">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="eb4ff-175">Общие правила определения типа для лямбда-выражений формулируются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eb4ff-175">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="eb4ff-176">лямбда-выражение должно содержать то же число параметров, что и тип делегата;</span><span class="sxs-lookup"><span data-stu-id="eb4ff-176">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="eb4ff-177">каждый входной параметр в лямбда-выражении должен быть неявно преобразуемым в соответствующий параметр делегата;</span><span class="sxs-lookup"><span data-stu-id="eb4ff-177">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="eb4ff-178">возвращаемое значение лямбда-выражения (если таковое имеется) должно быть неявно преобразуемым в возвращаемый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-178">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="eb4ff-179">Обратите внимание, что у лямбда-выражений нет типа, так как в системе общих типов изначально отсутствует такое понятие, как лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-179">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="eb4ff-180">Но применительно к лямбда-выражениям иногда бывает удобно оперировать понятием типа.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-180">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="eb4ff-181">При этом под типом понимается тип делегата или тип <xref:System.Linq.Expressions.Expression> , в который преобразуется лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-181">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a><span data-ttu-id="eb4ff-182">Запись внешних переменных и области видимости переменной в лямбда-выражениях</span><span class="sxs-lookup"><span data-stu-id="eb4ff-182">Capture of outer variables and variable scope in lambda expressions</span></span>

<span data-ttu-id="eb4ff-183">Лямбда-выражения могут ссылаться *на внешние переменные*.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-183">Lambdas can refer to *outer variables*.</span></span> <span data-ttu-id="eb4ff-184">Это переменные в области метода, в котором определено лямбда-выражение, или области типа, который содержит лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-184">These are the variables that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="eb4ff-185">Переменные, полученные таким способом, сохраняются для использования в лямбда-выражениях, даже если бы в ином случае они оказались за границами области действия и уничтожились сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-185">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="eb4ff-186">Внешняя переменная должна быть определенным образом присвоена, прежде чем она сможет использоваться в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-186">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="eb4ff-187">В следующем примере демонстрируются эти правила.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-187">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](snippets/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="eb4ff-188">Следующие правила применимы к области действия переменной в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-188">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="eb4ff-189">Захваченная переменная не будет уничтожена сборщиком мусора до тех пор, пока делегат, который на нее ссылается, не перейдет в статус подлежащего уничтожению при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-189">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="eb4ff-190">Переменные, представленные в лямбда-выражении, невидимы в заключающем методе.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-190">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="eb4ff-191">Лямбда-выражение не может непосредственно захватывать параметры [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md) или [out](../keywords/out-parameter-modifier.md) из заключающего метода.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-191">A lambda expression cannot directly capture an [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md), or [out](../keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="eb4ff-192">Оператор [return](../keywords/return.md) в лямбда-выражении не вызывает возврат значения заключающим методом.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-192">A [return](../keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="eb4ff-193">Лямбда-выражение не может содержать операторы [goto](../keywords/goto.md), [break](../keywords/break.md) или [continue](../keywords/continue.md), если целевой объект этого оператора перехода находится за пределами блока лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-193">A lambda expression cannot contain a [goto](../keywords/goto.md), [break](../keywords/break.md), or [continue](../keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="eb4ff-194">Если целевой объект находится внутри блока, использование оператора перехода за пределами лямбда-выражения также будет ошибкой.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-194">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="eb4ff-195">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="eb4ff-195">C# language specification</span></span>

<span data-ttu-id="eb4ff-196">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-196">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="eb4ff-197">Важная глава книги</span><span class="sxs-lookup"><span data-stu-id="eb4ff-197">Featured book chapter</span></span>

<span data-ttu-id="eb4ff-198">[Делегаты, события и лямбда-выражения](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="eb4ff-198">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4ff-199">См. также</span><span class="sxs-lookup"><span data-stu-id="eb4ff-199">See also</span></span>

- [<span data-ttu-id="eb4ff-200">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="eb4ff-200">C# reference</span></span>](../index.md)
- [<span data-ttu-id="eb4ff-201">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="eb4ff-201">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="eb4ff-202">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="eb4ff-202">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="eb4ff-203">Деревья выражений</span><span class="sxs-lookup"><span data-stu-id="eb4ff-203">Expression Trees</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="eb4ff-204">Локальные функции или лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="eb4ff-204">Local functions vs. lambda expressions</span></span>](../../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)
- [<span data-ttu-id="eb4ff-205">Примеры C# в Visual Studio 2008 (см. файлы примеров запросов LINQ и программу XQuery)</span><span class="sxs-lookup"><span data-stu-id="eb4ff-205">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
