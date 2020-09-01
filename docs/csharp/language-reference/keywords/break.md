---
description: Справочник по C#. Оператор break
title: Справочник по C#. Оператор break
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 7fd05889f684f7a2282de8222e1195898dead5b9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134748"
---
# <a name="break-c-reference"></a><span data-ttu-id="a40e7-103">break (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a40e7-103">break (C# Reference)</span></span>

<span data-ttu-id="a40e7-104">Оператор `break` завершает выполнение ближайшего оператора внешнего цикла или [switch](./switch.md), в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="a40e7-104">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="a40e7-105">Управление передается оператору, который расположен после завершенного оператора.</span><span class="sxs-lookup"><span data-stu-id="a40e7-105">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="a40e7-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a40e7-106">Example</span></span>

<span data-ttu-id="a40e7-107">В этом примере условный оператор содержит счетчик, который должен выполнять отсчет от 1 до 100; при этом оператор `break` завершает цикл после четырех отсчетов.</span><span class="sxs-lookup"><span data-stu-id="a40e7-107">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="a40e7-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a40e7-108">Example</span></span>

<span data-ttu-id="a40e7-109">В этом примере демонстрируется использование `break` в операторе [switch](./switch.md).</span><span class="sxs-lookup"><span data-stu-id="a40e7-109">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="a40e7-110">Если вы ввели `4`, выходные данные будут следующими:</span><span class="sxs-lookup"><span data-stu-id="a40e7-110">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="a40e7-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a40e7-111">Example</span></span>

<span data-ttu-id="a40e7-112">В этом примере оператор `break` используется для выхода из внутреннего вложенного цикла и возвращения управления внешнему циклу.</span><span class="sxs-lookup"><span data-stu-id="a40e7-112">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="a40e7-113">Элемент управления возвращается _только_ на один уровень выше во вложенных циклах.</span><span class="sxs-lookup"><span data-stu-id="a40e7-113">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="a40e7-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a40e7-114">Example</span></span>

<span data-ttu-id="a40e7-115">В этом примере оператор `break` используется только для выхода из текущей ветви во время каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="a40e7-115">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="a40e7-116">На сам цикл не влияют экземпляры `break`, принадлежащие вложенной инструкции [switch](./switch.md).</span><span class="sxs-lookup"><span data-stu-id="a40e7-116">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="a40e7-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a40e7-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a40e7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a40e7-118">See also</span></span>

- [<span data-ttu-id="a40e7-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a40e7-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a40e7-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a40e7-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a40e7-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a40e7-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a40e7-122">switch</span><span class="sxs-lookup"><span data-stu-id="a40e7-122">switch</span></span>](./switch.md)
