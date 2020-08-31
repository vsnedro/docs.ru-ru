---
description: Выражение nameof. Справочник по C#
title: Выражение nameof. Справочник по C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 04109cde2a1f9146bf9bb44f301272808797ded0
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118316"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="bc4ca-103">Выражение nameof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bc4ca-103">nameof expression (C# reference)</span></span>

<span data-ttu-id="bc4ca-104">Выражение `nameof` создает имя, тип или элемент переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="bc4ca-104">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="bc4ca-105">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="bc4ca-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="bc4ca-106">Если используются [буквальные идентификаторы](../tokens/verbatim.md), символ `@` не является частью имени, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bc4ca-106">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="bc4ca-107">Значение выражения `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc4ca-107">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="bc4ca-108">С помощью выражения `nameof` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="bc4ca-108">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="bc4ca-109">Выражение `nameof` доступно в C# версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="bc4ca-109">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bc4ca-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bc4ca-110">C# language specification</span></span>

<span data-ttu-id="bc4ca-111">См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bc4ca-111">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bc4ca-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bc4ca-112">See also</span></span>

- [<span data-ttu-id="bc4ca-113">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bc4ca-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bc4ca-114">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="bc4ca-114">C# operators and expressions</span></span>](index.md)
