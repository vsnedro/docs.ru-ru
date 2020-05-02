---
title: Выражение nameof. Справочник по C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135923"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="1b951-102">Выражение nameof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1b951-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="1b951-103">Выражение `nameof` создает имя, тип или элемент переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="1b951-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="1b951-104">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="1b951-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="1b951-105">Если используются [буквальные идентификаторы](../tokens/verbatim.md), символ `@` не является частью имени, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1b951-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="1b951-106">Значение выражения `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b951-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="1b951-107">С помощью выражения `nameof` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="1b951-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="1b951-108">Выражение `nameof` доступно в C# версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="1b951-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1b951-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1b951-109">C# language specification</span></span>

<span data-ttu-id="1b951-110">См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1b951-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b951-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1b951-111">See also</span></span>

- [<span data-ttu-id="1b951-112">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1b951-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1b951-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1b951-113">C# operators</span></span>](index.md)
