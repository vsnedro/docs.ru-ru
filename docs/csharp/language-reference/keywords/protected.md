---
description: Справочник по C#. Ключевое слово protected
title: Справочник по C#. Ключевое слово protected
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: af0c7ab5ebb6980bb0381e46fd38e9470f3a2152
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536760"
---
# <a name="protected-c-reference"></a><span data-ttu-id="2de87-103">protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2de87-103">protected (C# Reference)</span></span>

<span data-ttu-id="2de87-104">Ключевое слово `protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="2de87-104">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="2de87-105">Эта страница содержит доступ `protected`.</span><span class="sxs-lookup"><span data-stu-id="2de87-105">This page covers `protected` access.</span></span> <span data-ttu-id="2de87-106">Ключевое слово `protected` также является частью модификаторов доступа [`protected internal`](protected-internal.md) и [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="2de87-106">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="2de87-107">Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.</span><span class="sxs-lookup"><span data-stu-id="2de87-107">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="2de87-108">Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2de87-108">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="2de87-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2de87-109">Example</span></span>

<span data-ttu-id="2de87-110">Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса.</span><span class="sxs-lookup"><span data-stu-id="2de87-110">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="2de87-111">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="2de87-111">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="2de87-112">Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.</span><span class="sxs-lookup"><span data-stu-id="2de87-112">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="2de87-113">Элементы структуры защитить нельзя, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="2de87-113">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="2de87-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2de87-114">Example</span></span>

<span data-ttu-id="2de87-115">В этом примере класс `DerivedPoint` является производным от класса `Point`.</span><span class="sxs-lookup"><span data-stu-id="2de87-115">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="2de87-116">В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.</span><span class="sxs-lookup"><span data-stu-id="2de87-116">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="2de87-117">Если изменить уровни доступа `x` и `y` на [private](private.md), компилятор выдаст сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="2de87-117">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="2de87-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2de87-118">C# language specification</span></span>  

<span data-ttu-id="2de87-119">Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="2de87-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="2de87-120">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="2de87-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="2de87-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2de87-121">See also</span></span>

- [<span data-ttu-id="2de87-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2de87-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2de87-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2de87-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2de87-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="2de87-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2de87-125">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="2de87-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="2de87-126">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="2de87-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="2de87-127">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="2de87-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="2de87-128">public</span><span class="sxs-lookup"><span data-stu-id="2de87-128">public</span></span>](public.md)
- [<span data-ttu-id="2de87-129">private</span><span class="sxs-lookup"><span data-stu-id="2de87-129">private</span></span>](private.md)
- [<span data-ttu-id="2de87-130">internal</span><span class="sxs-lookup"><span data-stu-id="2de87-130">internal</span></span>](internal.md)
- <span data-ttu-id="2de87-131">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2de87-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
