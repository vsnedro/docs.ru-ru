---
title: Руководство по программированию на C#. Анонимные функции
description: Сведения об анонимных функциях. Для создания анонимной функции можно использовать лямбда-выражение или анонимный метод.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 1fde7d535054f09d55018a010468776622ebfba7
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063267"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="7ae2b-104">Руководство по программированию на C#. Анонимные функции</span><span class="sxs-lookup"><span data-stu-id="7ae2b-104">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="7ae2b-105">Анонимная функция — это "встроенный" оператор или выражение, которое может использоваться, когда тип делегата неизвестен.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-105">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="7ae2b-106">Ее можно использовать для инициализации именованного делегата или передать вместо типа именованного делегата в качестве параметра метода.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-106">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="7ae2b-107">Для создания анонимной функции можно использовать [лямбда-выражение](../../language-reference/operators/lambda-expressions.md) или [анонимный метод](../../language-reference/operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7ae2b-107">You can use a [lambda expression](../../language-reference/operators/lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="7ae2b-108">Мы советуем использовать лямбда-выражения, так как это более лаконичный способ написания встроенного кода.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-108">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="7ae2b-109">В отличие от анонимных методов некоторые типы лямбда-выражений можно преобразовывать в типы дерева выражений.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-109">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="7ae2b-110">Эволюция делегатов в C\#</span><span class="sxs-lookup"><span data-stu-id="7ae2b-110">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="7ae2b-111">В C# 1.0 экземпляр делегата создавался путем его явной инициализации с помощью метода, который был определен в другом месте кода.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-111">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="7ae2b-112">В C# 2.0 введена концепция анонимных методов как способа написания неименованных встроенных блоков операторов, которые могут быть выполнены в вызове делегата.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-112">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="7ae2b-113">В C# 3.0 введены лямбда-выражения, по сути аналогичные анонимным методам, но более выразительные и четкие.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-113">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="7ae2b-114">Эти две функции собирательно называют *анонимными функциями*.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-114">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="7ae2b-115">Как правило, в приложениях, предназначенных для .NET Framework 3.5 и более поздних версий, следует использовать лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="7ae2b-115">In general, applications that target .NET Framework 3.5 or later should use lambda expressions.</span></span>  
  
 <span data-ttu-id="7ae2b-116">В следующем примере демонстрируется эволюция создания делегата от C# 1.0 до C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="7ae2b-116">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="7ae2b-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7ae2b-117">C# language specification</span></span>

<span data-ttu-id="7ae2b-118">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7ae2b-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ae2b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae2b-119">See also</span></span>

- [<span data-ttu-id="7ae2b-120">Инструкции, выражения и операторы</span><span class="sxs-lookup"><span data-stu-id="7ae2b-120">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="7ae2b-121">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="7ae2b-121">Lambda Expressions</span></span>](../../language-reference/operators/lambda-expressions.md)
- [<span data-ttu-id="7ae2b-122">Делегаты</span><span class="sxs-lookup"><span data-stu-id="7ae2b-122">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="7ae2b-123">Деревья выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="7ae2b-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
