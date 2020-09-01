---
description: Справочник по C#. while
title: Справочник по C#. while
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 97299f9ac6f2cdd6bbddf831b3ee2ad711935fbe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141872"
---
# <a name="while-c-reference"></a><span data-ttu-id="92011-103">while (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="92011-103">while (C# Reference)</span></span>

<span data-ttu-id="92011-104">Оператор `while` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="92011-104">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="92011-105">Так как это выражение оценивается перед каждым выполнением цикла, цикл `while` выполняется ноль или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="92011-105">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="92011-106">Это отличает его от цикла [do](do.md), который выполняется от одного до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="92011-106">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="92011-107">В любой точке блока операторов `while` можно разорвать цикл с помощью оператора [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="92011-107">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="92011-108">Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="92011-108">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="92011-109">Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="92011-109">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="92011-110">В противном случае выполнение продолжается с первого оператора после цикла.</span><span class="sxs-lookup"><span data-stu-id="92011-110">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="92011-111">Можно также выйти из цикла `while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="92011-111">You can also exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="92011-112">Пример</span><span class="sxs-lookup"><span data-stu-id="92011-112">Example</span></span>

<span data-ttu-id="92011-113">В следующем примере показано применение оператора `while`.</span><span class="sxs-lookup"><span data-stu-id="92011-113">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="92011-114">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="92011-114">Select **Run** to run the example code.</span></span> <span data-ttu-id="92011-115">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="92011-115">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](snippets/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="92011-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="92011-116">C# language specification</span></span>

<span data-ttu-id="92011-117">Дополнительные сведения см. в разделе [Оператор while](~/_csharplang/spec/statements.md#the-while-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="92011-117">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="92011-118">См. также</span><span class="sxs-lookup"><span data-stu-id="92011-118">See also</span></span>

- [<span data-ttu-id="92011-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="92011-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="92011-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="92011-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="92011-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="92011-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="92011-122">Оператор do</span><span class="sxs-lookup"><span data-stu-id="92011-122">do statement</span></span>](do.md)
