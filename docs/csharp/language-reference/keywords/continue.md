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
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877656"
---
# <a name="continue-c-reference"></a><span data-ttu-id="f368a-103">continue (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f368a-103">continue (C# Reference)</span></span>

<span data-ttu-id="f368a-104">Оператор `continue` передает управление следующей итерации вложенного оператора [while](./while.md), [do](./do.md), [for](./for.md) или [foreach](./foreach-in.md), в котором она встречается.</span><span class="sxs-lookup"><span data-stu-id="f368a-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="f368a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f368a-105">Example</span></span>

<span data-ttu-id="f368a-106">В этом примере инициализируется счетчик, выполняющий отсчет от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="f368a-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="f368a-107">Благодаря использованию оператора `continue` в сочетании с выражением `(i < 9)` операторы между `continue` и концом текста `for` пропускаются в итерациях, в которых `i` меньше 9.</span><span class="sxs-lookup"><span data-stu-id="f368a-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped in the iterations where `i` is less than 9.</span></span> <span data-ttu-id="f368a-108">В двух последних итерациях цикла `for` (когда i == 9 и i == 10) инструкция `continue` не выполняется, а значение `i` выводится в консоль.</span><span class="sxs-lookup"><span data-stu-id="f368a-108">In the last two iterations of the `for` loop (where i == 9 and i == 10), the `continue` statement is not executed and the value of `i` is printed to the console.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="f368a-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f368a-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f368a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f368a-110">See also</span></span>

- [<span data-ttu-id="f368a-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f368a-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f368a-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f368a-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f368a-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f368a-113">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="f368a-114">Оператор break</span><span class="sxs-lookup"><span data-stu-id="f368a-114">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
