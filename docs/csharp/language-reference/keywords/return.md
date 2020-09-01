---
description: Справочник по C#. Оператор return
title: Справочник по C#. Оператор return
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 486db846304c0972942ff58f3d5b276083681abe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137008"
---
# <a name="return-c-reference"></a><span data-ttu-id="9fd46-103">return (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9fd46-103">return (C# Reference)</span></span>

<span data-ttu-id="9fd46-104">Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу.</span><span class="sxs-lookup"><span data-stu-id="9fd46-104">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="9fd46-105">Он также возвращает необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="9fd46-105">It can also return an optional value.</span></span> <span data-ttu-id="9fd46-106">Если метод имеет тип `void`, оператор `return` можно опустить.</span><span class="sxs-lookup"><span data-stu-id="9fd46-106">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="9fd46-107">Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="9fd46-107">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="9fd46-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9fd46-108">Example</span></span>

 <span data-ttu-id="9fd46-109">В приведенном ниже примере метод `CalculateArea()` возвращает локальную переменную `area` в виде значения `double`.</span><span class="sxs-lookup"><span data-stu-id="9fd46-109">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="9fd46-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9fd46-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9fd46-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9fd46-111">See also</span></span>

- [<span data-ttu-id="9fd46-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9fd46-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9fd46-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9fd46-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9fd46-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9fd46-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9fd46-115">Оператор return</span><span class="sxs-lookup"><span data-stu-id="9fd46-115">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
