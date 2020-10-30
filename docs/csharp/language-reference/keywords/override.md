---
description: Справочник по C#. Модификатор override
title: Справочник по C#. Модификатор override
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434878"
---
# <a name="override-c-reference"></a><span data-ttu-id="e60da-103">override (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e60da-103">override (C# reference)</span></span>

<span data-ttu-id="e60da-104">Модификатор `override` требуется для расширения или изменения абстрактной или виртуальной реализации унаследованного метода, свойства, индексатора или события.</span><span class="sxs-lookup"><span data-stu-id="e60da-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

<span data-ttu-id="e60da-105">В следующем примере класс `Square` должен предоставить переопределенную реализацию `GetArea`, так как `GetArea` является унаследованным от абстрактного класса `Shape`:</span><span class="sxs-lookup"><span data-stu-id="e60da-105">In the following example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="e60da-106">Метод `override` предоставляет новую реализацию метода, унаследованного от базового класса.</span><span class="sxs-lookup"><span data-stu-id="e60da-106">An `override` method provides a new implementation of the method inherited from a base class.</span></span> <span data-ttu-id="e60da-107">Метод, переопределенный объявлением `override`, называется переопределенным базовым методом.</span><span class="sxs-lookup"><span data-stu-id="e60da-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="e60da-108">Метод `override` должен иметь ту же сигнатуру, что и переопределенный базовый метод.</span><span class="sxs-lookup"><span data-stu-id="e60da-108">An `override` method must have the same signature as the overridden base method.</span></span> <span data-ttu-id="e60da-109">Начиная с версии C# 9.0, методы `override` поддерживают ковариантные типы возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="e60da-109">Beginning with C# 9.0, `override` methods support covariant return types.</span></span> <span data-ttu-id="e60da-110">В частности, тип возвращаемого значения метода `override` может быть производным от типа возвращаемого значения соответствующего базового метода.</span><span class="sxs-lookup"><span data-stu-id="e60da-110">In particular, the return type of an `override` method can derive from the return type of the corresponding base method.</span></span> <span data-ttu-id="e60da-111">В C# 8.0 и более ранних версий типы возвращаемых значений метода `override` и переопределенного базового метода должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="e60da-111">In C# 8.0 and earlier, the return types of an `override` method and the overridden base method must be the same.</span></span>

<span data-ttu-id="e60da-112">Невиртуальный или статический метод нельзя переопределить.</span><span class="sxs-lookup"><span data-stu-id="e60da-112">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="e60da-113">Переопределенный базовый метод должен иметь тип `virtual`, `abstract` или `override`.</span><span class="sxs-lookup"><span data-stu-id="e60da-113">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="e60da-114">Объявление `override` не может изменить доступность метода `virtual`.</span><span class="sxs-lookup"><span data-stu-id="e60da-114">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="e60da-115">Методы `override` и `virtual` должны иметь одинаковый [модификатор уровня доступа](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-115">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="e60da-116">Модификаторы `new`, `static` и `virtual` нельзя использовать для изменения метода `override`.</span><span class="sxs-lookup"><span data-stu-id="e60da-116">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="e60da-117">Переопределяющее объявление свойства должно задавать такие же модификатор уровня доступа, тип и имя, которые имеются у унаследованного свойства.</span><span class="sxs-lookup"><span data-stu-id="e60da-117">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property.</span></span> <span data-ttu-id="e60da-118">Начиная с версии C# 9.0, переопределяющие свойства только для чтения поддерживают ковариантные типы возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="e60da-118">Beginning with C# 9.0, read-only overriding properties support covariant return types.</span></span> <span data-ttu-id="e60da-119">Переопределенное свойство должно быть `virtual`, `abstract` или `override`.</span><span class="sxs-lookup"><span data-stu-id="e60da-119">The overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="e60da-120">Дополнительные сведения об использовании ключевого слова `override` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-120">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span> <span data-ttu-id="e60da-121">Дополнительные сведения о наследовании см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-121">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

## <a name="example"></a><span data-ttu-id="e60da-122">Пример</span><span class="sxs-lookup"><span data-stu-id="e60da-122">Example</span></span>

<span data-ttu-id="e60da-123">В этом примере определяется базовый класс с именем `Employee` и производный класс с именем `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="e60da-123">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="e60da-124">Класс `SalesEmployee` включает дополнительное поле `salesbonus`, для использования которого переопределяется метод `CalculatePay`.</span><span class="sxs-lookup"><span data-stu-id="e60da-124">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="e60da-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e60da-125">C# language specification</span></span>

<span data-ttu-id="e60da-126">Дополнительные сведения см. в разделе [Методы переопределения](~/_csharplang/spec/classes.md#override-methods) статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-126">For more information, see the [Override methods](~/_csharplang/spec/classes.md#override-methods) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="e60da-127">Дополнительные сведения о ковариантных типах возвращаемых значений см. в [примечании к функциям](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-127">For more information about covariant return types, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e60da-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e60da-128">See also</span></span>

- [<span data-ttu-id="e60da-129">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e60da-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e60da-130">Наследование</span><span class="sxs-lookup"><span data-stu-id="e60da-130">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="e60da-131">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="e60da-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="e60da-132">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="e60da-132">Modifiers</span></span>](index.md)
- [<span data-ttu-id="e60da-133">abstract</span><span class="sxs-lookup"><span data-stu-id="e60da-133">abstract</span></span>](abstract.md)
- [<span data-ttu-id="e60da-134">virtual</span><span class="sxs-lookup"><span data-stu-id="e60da-134">virtual</span></span>](virtual.md)
- [<span data-ttu-id="e60da-135">new (модификатор)</span><span class="sxs-lookup"><span data-stu-id="e60da-135">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="e60da-136">Полиморфизм</span><span class="sxs-lookup"><span data-stu-id="e60da-136">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
