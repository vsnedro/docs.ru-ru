---
description: Оператор goto. Справочник по C#
title: Оператор goto. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128430"
---
# <a name="goto-c-reference"></a><span data-ttu-id="54c22-103">goto (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="54c22-103">goto (C# Reference)</span></span>

<span data-ttu-id="54c22-104">Оператор `goto` передает управление программой непосредственно оператору с меткой.</span><span class="sxs-lookup"><span data-stu-id="54c22-104">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="54c22-105">Оператор `goto` часто используется для передачи управления определенной метке смены регистра или метке по умолчанию в операторе `switch`.</span><span class="sxs-lookup"><span data-stu-id="54c22-105">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="54c22-106">`goto` Этот оператор также удобно использовать для выхода из глубоко вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="54c22-106">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="54c22-107">Пример</span><span class="sxs-lookup"><span data-stu-id="54c22-107">Example</span></span>

<span data-ttu-id="54c22-108">В следующем примере демонстрируется использование `goto` в операторе [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="54c22-108">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="54c22-109">Пример</span><span class="sxs-lookup"><span data-stu-id="54c22-109">Example</span></span>

<span data-ttu-id="54c22-110">В следующем примере демонстрируется использование `goto` для выхода из вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="54c22-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="54c22-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="54c22-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="54c22-112">См. также</span><span class="sxs-lookup"><span data-stu-id="54c22-112">See also</span></span>

- [<span data-ttu-id="54c22-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="54c22-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="54c22-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="54c22-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="54c22-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="54c22-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="54c22-116">Оператор goto (C++)</span><span class="sxs-lookup"><span data-stu-id="54c22-116">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
