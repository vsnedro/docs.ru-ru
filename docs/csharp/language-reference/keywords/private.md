---
description: Справочник по C#. Ключевое слово private
title: Справочник по C#. Ключевое слово private
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: e6f40712fd2cca6d7b1f64760f1c6c5dd5c71370
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139402"
---
# <a name="private-c-reference"></a><span data-ttu-id="bcaaa-103">private (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bcaaa-103">private (C# Reference)</span></span>

<span data-ttu-id="bcaaa-104">Ключевое слово `private` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-104">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="bcaaa-105">Эта страница содержит доступ `private`.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-105">This page covers `private` access.</span></span> <span data-ttu-id="bcaaa-106">Ключевое слово `private` также является частью модификатора доступа [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="bcaaa-106">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="bcaaa-107">Закрытый доступ является уровнем доступа с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-107">Private access is the least permissive access level.</span></span> <span data-ttu-id="bcaaa-108">Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bcaaa-108">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="bcaaa-109">Вложенные типы в том же теле могут также обращаться к таким закрытым членам.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-109">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="bcaaa-110">Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-110">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="bcaaa-111">Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](accessibility-levels.md) и [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="bcaaa-111">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="bcaaa-112">Пример</span><span class="sxs-lookup"><span data-stu-id="bcaaa-112">Example</span></span>

<span data-ttu-id="bcaaa-113">В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-113">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="bcaaa-114">Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-114">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="bcaaa-115">Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-115">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="bcaaa-116">Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-116">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="bcaaa-117">(Дополнительные сведения см. в разделе [Свойства](../../programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="bcaaa-117">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="bcaaa-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bcaaa-118">C# language specification</span></span>  

<span data-ttu-id="bcaaa-119">Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="bcaaa-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="bcaaa-120">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="bcaaa-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcaaa-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bcaaa-121">See also</span></span>

- [<span data-ttu-id="bcaaa-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bcaaa-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bcaaa-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bcaaa-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bcaaa-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="bcaaa-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bcaaa-125">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="bcaaa-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="bcaaa-126">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="bcaaa-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="bcaaa-127">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="bcaaa-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="bcaaa-128">public</span><span class="sxs-lookup"><span data-stu-id="bcaaa-128">public</span></span>](public.md)
- [<span data-ttu-id="bcaaa-129">protected</span><span class="sxs-lookup"><span data-stu-id="bcaaa-129">protected</span></span>](protected.md)
- [<span data-ttu-id="bcaaa-130">internal</span><span class="sxs-lookup"><span data-stu-id="bcaaa-130">internal</span></span>](internal.md)
