---
description: Справочник по C#. Оператор continue
title: Справочник по C#. Оператор continue
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128443"
---
# <a name="continue-c-reference"></a><span data-ttu-id="b0b3b-103">continue (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b0b3b-103">continue (C# Reference)</span></span>

<span data-ttu-id="b0b3b-104">Оператор `continue` передает управление следующей итерации вложенного оператора [while](./while.md), [do](./do.md), [for](./for.md) или [foreach](./foreach-in.md), в котором она встречается.</span><span class="sxs-lookup"><span data-stu-id="b0b3b-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="b0b3b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b0b3b-105">Example</span></span>

<span data-ttu-id="b0b3b-106">В этом примере инициализируется счетчик, выполняющий отсчет от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="b0b3b-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="b0b3b-107">Благодаря использованию оператора `continue` в сочетании с выражением `(i < 9)` операторы между `continue` и концом текста `for` пропускаются.</span><span class="sxs-lookup"><span data-stu-id="b0b3b-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="b0b3b-108">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b0b3b-108">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b0b3b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b0b3b-109">See also</span></span>

- [<span data-ttu-id="b0b3b-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b0b3b-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b0b3b-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b0b3b-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b0b3b-112">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b0b3b-112">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b0b3b-113">Оператор break</span><span class="sxs-lookup"><span data-stu-id="b0b3b-113">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
