---
description: Справочник по C#. Оператор try-catch-finally
title: Справочник по C#. Оператор try-catch-finally
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 6e85330e12c53e0728ef671530709748090ebe02
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142015"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="b00e2-103">try-catch-finally (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b00e2-103">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="b00e2-104">Чаще всего `catch` и `finally` применяются вместе для получения и использования ресурсов в блоке `try`, устранения исключительных обстоятельств в блоке `catch` и освобождения ресурсов в блоке `finally`.</span><span class="sxs-lookup"><span data-stu-id="b00e2-104">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="b00e2-105">Дополнительные сведения и примеры повторного создания исключений см. в разделах [try-catch](try-catch.md) и [Порождение исключений](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="b00e2-105">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="b00e2-106">Дополнительные сведения о блоке `finally` см. в разделе [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="b00e2-106">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="b00e2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b00e2-107">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="b00e2-108">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b00e2-108">C# language specification</span></span>

<span data-ttu-id="b00e2-109">Дополнительные сведения см. в разделе [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в документации [Спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b00e2-109">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b00e2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b00e2-110">See also</span></span>

- [<span data-ttu-id="b00e2-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b00e2-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b00e2-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b00e2-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b00e2-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b00e2-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b00e2-114">Операторы try, throw и catch (C++)</span><span class="sxs-lookup"><span data-stu-id="b00e2-114">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="b00e2-115">throw</span><span class="sxs-lookup"><span data-stu-id="b00e2-115">throw</span></span>](throw.md)
- [<span data-ttu-id="b00e2-116">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="b00e2-116">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="b00e2-117">Оператор using</span><span class="sxs-lookup"><span data-stu-id="b00e2-117">using Statement</span></span>](using-statement.md)
