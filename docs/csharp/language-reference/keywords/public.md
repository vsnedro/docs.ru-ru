---
description: Справочник по C#. Ключевое слово public
title: Справочник по C#. Ключевое слово public
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 26edaf7538d11d082a4b8863228213c3ebc46937
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122346"
---
# <a name="public-c-reference"></a><span data-ttu-id="4e594-103">public (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4e594-103">public (C# Reference)</span></span>

<span data-ttu-id="4e594-104">Ключевое слово `public` является модификатором доступа для типов и членов типов.</span><span class="sxs-lookup"><span data-stu-id="4e594-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="4e594-105">Общий доступ является уровнем доступа с максимальными правами.</span><span class="sxs-lookup"><span data-stu-id="4e594-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="4e594-106">Ограничений доступа к общим членам не существует, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4e594-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="4e594-107">Дополнительные сведения см. в разделах [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4e594-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="4e594-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4e594-108">Example</span></span>

<span data-ttu-id="4e594-109">В следующем примере объявляются два класса: `PointTest` и `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="4e594-109">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="4e594-110">Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="4e594-110">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="4e594-111">Если уровень доступа `public` изменить на [private](private.md) или [protected](protected.md), будет выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="4e594-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="4e594-112">"PointTest.y" недоступен из-за его уровня защиты.</span><span class="sxs-lookup"><span data-stu-id="4e594-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4e594-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4e594-113">C# language specification</span></span>  

<span data-ttu-id="4e594-114">Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="4e594-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="4e594-115">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="4e594-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e594-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4e594-116">See also</span></span>

- [<span data-ttu-id="4e594-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4e594-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4e594-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4e594-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4e594-119">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="4e594-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="4e594-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="4e594-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4e594-121">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="4e594-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="4e594-122">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="4e594-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="4e594-123">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="4e594-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="4e594-124">private</span><span class="sxs-lookup"><span data-stu-id="4e594-124">private</span></span>](private.md)
- [<span data-ttu-id="4e594-125">protected</span><span class="sxs-lookup"><span data-stu-id="4e594-125">protected</span></span>](protected.md)
- [<span data-ttu-id="4e594-126">internal</span><span class="sxs-lookup"><span data-stu-id="4e594-126">internal</span></span>](internal.md)
