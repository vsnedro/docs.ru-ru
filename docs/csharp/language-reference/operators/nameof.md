---
title: Выражение nameof. Справочник по C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916776"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="92da2-102">Выражение nameof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="92da2-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="92da2-103">Выражение `nameof` создает имя, тип или элемент переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="92da2-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="92da2-104">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="92da2-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="92da2-105">Если используются [буквальные идентификаторы](../tokens/verbatim.md), символ `@` не является частью имени, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="92da2-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="92da2-106">Значение выражения `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="92da2-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="92da2-107">С помощью выражения `nameof` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="92da2-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="92da2-108">Выражение `nameof` доступно в C# версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="92da2-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="92da2-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="92da2-109">C# language specification</span></span>

<span data-ttu-id="92da2-110">См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="92da2-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92da2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="92da2-111">See also</span></span>

- [<span data-ttu-id="92da2-112">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="92da2-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="92da2-113">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="92da2-113">C# operators and expressions</span></span>](index.md)
