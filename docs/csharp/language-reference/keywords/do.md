---
description: Справочник по C#. do
title: Справочник по C#. do
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 601231f23a58e8af8339a733677f0bbd92bb4ffc
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126961"
---
# <a name="do-c-reference"></a><span data-ttu-id="e5133-103">do (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e5133-103">do (C# Reference)</span></span>

<span data-ttu-id="e5133-104">Оператор `do` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="e5133-104">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="e5133-105">Так как это выражение оценивается после каждого выполнения цикла, цикл `do-while` выполняется один или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="e5133-105">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="e5133-106">Это отличает его от цикла [while](while.md), который выполняется от нуля до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="e5133-106">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="e5133-107">В любой точке блока операторов `do` можно разорвать цикл с помощью оператора [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="e5133-107">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="e5133-108">Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="e5133-108">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="e5133-109">Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="e5133-109">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="e5133-110">В противном случае выполнение продолжается с первого оператора после цикла.</span><span class="sxs-lookup"><span data-stu-id="e5133-110">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="e5133-111">Можно также выйти из цикла `do-while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="e5133-111">You can also exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="e5133-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e5133-112">Example</span></span>

<span data-ttu-id="e5133-113">В следующем примере показано применение оператора `do`.</span><span class="sxs-lookup"><span data-stu-id="e5133-113">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="e5133-114">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="e5133-114">Select **Run** to run the example code.</span></span> <span data-ttu-id="e5133-115">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="e5133-115">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](snippets/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="e5133-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e5133-116">C# language specification</span></span>

<span data-ttu-id="e5133-117">Дополнительные сведения см. в разделе [Оператор do](~/_csharplang/spec/statements.md#the-do-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="e5133-117">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5133-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e5133-118">See also</span></span>

- [<span data-ttu-id="e5133-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e5133-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e5133-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e5133-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e5133-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e5133-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e5133-122">Оператор while</span><span class="sxs-lookup"><span data-stu-id="e5133-122">while statement</span></span>](while.md)
