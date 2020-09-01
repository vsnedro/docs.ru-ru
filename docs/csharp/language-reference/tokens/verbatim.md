---
description: '@. Справочник по C#'
title: '@. Справочник по C#'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: 7d78b28479ed6128321207073dc94976710f10b6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138908"
---
# <a name="-c-reference"></a><span data-ttu-id="466a4-103">@ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="466a4-103">@ (C# Reference)</span></span>

<span data-ttu-id="466a4-104">Специальный символ `@` является буквальным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="466a4-104">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="466a4-105">Его можно применять в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="466a4-105">It can be used in the following ways:</span></span>

1. <span data-ttu-id="466a4-106">Чтобы использовать ключевые слова C# в качестве идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="466a4-106">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="466a4-107">Символ `@` предшествует элементу кода, который компилятор должен интерпретировать как идентификатор, а не ключевое слово C#.</span><span class="sxs-lookup"><span data-stu-id="466a4-107">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="466a4-108">В следующем примере символ `@` используется для определения идентификатора `for`, используемого в цикле `for`.</span><span class="sxs-lookup"><span data-stu-id="466a4-108">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="466a4-109">Чтобы указать, что строковый литерал следует интерпретировать буквально.</span><span class="sxs-lookup"><span data-stu-id="466a4-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="466a4-110">Символ `@` в этом случае определяет *буквальный строковый литерал*.</span><span class="sxs-lookup"><span data-stu-id="466a4-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="466a4-111">Простые escape-последовательности (например, `"\\"` для обратной косой черты), шестнадцатеричные escape-последовательности (например, `"\x0041"` для прописной буквы A) и escape-последовательности Юникода (например, `"\u0041"` для прописной буквы A) интерпретируются буквально.</span><span class="sxs-lookup"><span data-stu-id="466a4-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="466a4-112">Только escape-последовательность кавычек (`""`) не интерпретируется буквально. Она создает одну двойную кавычку.</span><span class="sxs-lookup"><span data-stu-id="466a4-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces one double quotation mark.</span></span> <span data-ttu-id="466a4-113">Кроме того, в случае буквальной [интерполированной строки](interpolated.md) escape-последовательности фигурных скобок (`{{` и `}}`) не интерпретируются буквально; они создают одну фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="466a4-113">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="466a4-114">В следующем примере определяются два идентичных пути к файлам: один с помощью обычного строкового литерала, а другой — с помощью буквального строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="466a4-114">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="466a4-115">Это один из наиболее распространенных способов использования буквальных строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="466a4-115">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="466a4-116">В следующем примере показан результат определения обычного строкового литерала и буквального строкового литерала, содержащий идентичные последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="466a4-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="466a4-117">Чтобы позволить компилятору различать атрибуты в случае конфликта имен.</span><span class="sxs-lookup"><span data-stu-id="466a4-117">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="466a4-118">Атрибут класса, который наследует от <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="466a4-118">An attribute is a class that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="466a4-119">Имя его типа, как правило, содержит суффикс **Attribute**, несмотря на то, что компилятор не выполняет это соглашение.</span><span class="sxs-lookup"><span data-stu-id="466a4-119">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="466a4-120">Затем на атрибут можно ссылаться в коде либо по его полному имени типа (например, `[InfoAttribute]`), либо по сокращенному имени (например, `[Info]`).</span><span class="sxs-lookup"><span data-stu-id="466a4-120">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="466a4-121">Однако если два сокращенных имени типов совпадают и одно имя типа содержит суффикс **Attribute**, а другое — нет, возникает конфликт имен.</span><span class="sxs-lookup"><span data-stu-id="466a4-121">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="466a4-122">Например, приведенный ниже код не может быть скомпилирован, так как компилятору не удается определить, какой атрибут — `Info` или `InfoAttribute` — применен к классу `Example`.</span><span class="sxs-lookup"><span data-stu-id="466a4-122">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span> <span data-ttu-id="466a4-123">См. [CS1614](../compiler-messages/cs1614.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="466a4-123">See [CS1614](../compiler-messages/cs1614.md) for more information.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a><span data-ttu-id="466a4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="466a4-124">See also</span></span>

- [<span data-ttu-id="466a4-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="466a4-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="466a4-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="466a4-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="466a4-127">Специальные символы в C#</span><span class="sxs-lookup"><span data-stu-id="466a4-127">C# Special Characters</span></span>](./index.md)
