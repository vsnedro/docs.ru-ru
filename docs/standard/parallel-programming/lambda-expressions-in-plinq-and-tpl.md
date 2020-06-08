---
title: Лямбда-выражения в PLINQ и библиотеке параллельных задач
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 3d985a003fe613699c89e38583f84be9e21b383d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290672"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="2e183-102">Лямбда-выражения в PLINQ и библиотеке параллельных задач</span><span class="sxs-lookup"><span data-stu-id="2e183-102">Lambda Expressions in PLINQ and TPL</span></span>

<span data-ttu-id="2e183-103">Библиотека параллельных задач (TPL) содержит множество методов, которые принимают в качестве входных параметров один из делегатов семейства <xref:System.Func%601?displayProperty=nameWithType> или <xref:System.Action?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e183-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="2e183-104">Используйте эти делегаты для передачи пользовательской программной логики в параллельный цикл, задачу или запрос.</span><span class="sxs-lookup"><span data-stu-id="2e183-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="2e183-105">В примерах кода для библиотеки параллельных задач и PLINQ лямбда-выражения используются для создания экземпляров этих делегатов как встроенных блоков кода.</span><span class="sxs-lookup"><span data-stu-id="2e183-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="2e183-106">В этом разделе дается краткое введение в делегаты Func и Action и демонстрируется использование лямбда-выражений в библиотеке параллельных задач и PLINQ.</span><span class="sxs-lookup"><span data-stu-id="2e183-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>

> [!NOTE]
> <span data-ttu-id="2e183-107">Дополнительные сведения о делегатах см. в разделах [Делегаты](../../csharp/programming-guide/delegates/index.md) и [Делегаты](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e183-107">For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="2e183-108">Дополнительные сведения о лямбда-выражениях в C# и Visual Basic см. в разделах [Лямбда-выражения](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) и [Лямбда-выражения](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2e183-108">For more information about lambda expressions in C# and Visual Basic, see [Lambda Expressions](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="func-delegate"></a><span data-ttu-id="2e183-109">Делегат Func</span><span class="sxs-lookup"><span data-stu-id="2e183-109">Func Delegate</span></span>

<span data-ttu-id="2e183-110">Делегат `Func` инкапсулирует метод, который возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="2e183-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="2e183-111">В сигнатуре `Func` последний или крайний справа тип параметра всегда указывает возвращаемый тип.</span><span class="sxs-lookup"><span data-stu-id="2e183-111">In a `Func` signature, the last, or rightmost, type parameter always specifies the return type.</span></span> <span data-ttu-id="2e183-112">Распространенной причиной ошибок компилятора является попытка передать в <xref:System.Func%602?displayProperty=nameWithType> два входных параметра. На самом деле этот тип принимает только один входной параметр.</span><span class="sxs-lookup"><span data-stu-id="2e183-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="2e183-113">.NET определяет 17 версий `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType> и т. д. до <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e183-113">.NET defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>

## <a name="action-delegate"></a><span data-ttu-id="2e183-114">Делегат Action</span><span class="sxs-lookup"><span data-stu-id="2e183-114">Action Delegate</span></span>

<span data-ttu-id="2e183-115">Делегат <xref:System.Action?displayProperty=nameWithType> инкапсулирует метод (Sub в Visual Basic), который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="2e183-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in Visual Basic) that does not return a value.</span></span> <span data-ttu-id="2e183-116">В сигнатуре типа `Action` параметры типа представляют только входные параметры.</span><span class="sxs-lookup"><span data-stu-id="2e183-116">In an `Action` type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="2e183-117">Как и `Func`, .NET определяет 17 версий делегата `Action`, начиная с версии без параметров типа и заканчивая версией с 16 параметрами типа.</span><span class="sxs-lookup"><span data-stu-id="2e183-117">Like `Func`, .NET defines 17 versions of `Action`, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>

## <a name="example"></a><span data-ttu-id="2e183-118">Пример</span><span class="sxs-lookup"><span data-stu-id="2e183-118">Example</span></span>

<span data-ttu-id="2e183-119">Следующий пример демонстрирует метод <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> позволяющий выразить делегаты Func и Action через лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="2e183-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a><span data-ttu-id="2e183-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2e183-120">See also</span></span>

- [<span data-ttu-id="2e183-121">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="2e183-121">Parallel Programming</span></span>](index.md)
