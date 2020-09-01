---
description: Справочник по C#. Ключевое слово unsafe
title: Справочник по C#. Ключевое слово unsafe
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 2e047a4cff77877862c5cbbb5e49eb1a75b42499
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141963"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="f6d64-103">unsafe (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f6d64-103">unsafe (C# Reference)</span></span>

<span data-ttu-id="f6d64-104">Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для выполнения любых операций с применением указателей.</span><span class="sxs-lookup"><span data-stu-id="f6d64-104">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="f6d64-105">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6d64-105">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="f6d64-106">В объявлении типа или члена типа можно использовать модификатор `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="f6d64-106">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="f6d64-107">Все текстовое пространство типа или члена типа считается небезопасным контекстом.</span><span class="sxs-lookup"><span data-stu-id="f6d64-107">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="f6d64-108">Например, следующий метод объявлен с модификатором `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="f6d64-108">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="f6d64-109">Область небезопасного контекста простирается от списка параметров до конца метода, поэтому в списке параметров можно также использовать указатели:</span><span class="sxs-lookup"><span data-stu-id="f6d64-109">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="f6d64-110">Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок.</span><span class="sxs-lookup"><span data-stu-id="f6d64-110">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="f6d64-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="f6d64-111">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="f6d64-112">Чтобы скомпилировать небезопасный код, необходимо указать параметр компилятора [`-unsafe`](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f6d64-112">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f6d64-113">Небезопасный код не проверяется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f6d64-113">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="f6d64-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f6d64-114">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="f6d64-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f6d64-115">C# language specification</span></span>

<span data-ttu-id="f6d64-116">Дополнительные сведения см. в разделе [Небезопасный код](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="f6d64-116">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="f6d64-117">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="f6d64-117">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6d64-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f6d64-118">See also</span></span>

- [<span data-ttu-id="f6d64-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f6d64-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6d64-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f6d64-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f6d64-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f6d64-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f6d64-122">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="f6d64-122">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="f6d64-123">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="f6d64-123">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="f6d64-124">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="f6d64-124">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
