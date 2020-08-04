---
title: Руководство по программированию на C#. Индексаторы
description: Индексаторы в C# позволяют индексировать экземпляры класса или структуры так же, как и массивы. Вы можете задать или получить индексированное значение, не указывая тип или член экземпляра.
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: 07e0ae4294373817e10bb79920c73ec1e275d169
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303118"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="98f64-104">Индексаторы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="98f64-104">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="98f64-105">Индексаторы позволяют индексировать экземпляры класса или структуры точно так же, как и массивы.</span><span class="sxs-lookup"><span data-stu-id="98f64-105">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="98f64-106">Индексированное значение можно задавать или получать без явного указания типа или экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="98f64-106">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="98f64-107">Индексаторы действуют как [свойства](../classes-and-structs/properties.md), за исключением того, что их акцессоры принимают параметры.</span><span class="sxs-lookup"><span data-stu-id="98f64-107">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="98f64-108">В следующем примере определяется универсальный класс с простыми акцессорами [get](../../language-reference/keywords/get.md) и [set](../../language-reference/keywords/set.md) для назначения и получения значений.</span><span class="sxs-lookup"><span data-stu-id="98f64-108">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="98f64-109">Класс `Program` создает экземпляр этого класса для хранения строк.</span><span class="sxs-lookup"><span data-stu-id="98f64-109">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="98f64-110">Дополнительные примеры см. в разделе [Связанные разделы](./index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="98f64-110">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="98f64-111">Определения текста выражений</span><span class="sxs-lookup"><span data-stu-id="98f64-111">Expression Body Definitions</span></span>  

<span data-ttu-id="98f64-112">Довольно часто акцессор get или set индексатора состоит из одной инструкции, которая просто возвращает или задает значение.</span><span class="sxs-lookup"><span data-stu-id="98f64-112">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="98f64-113">Члены, воплощающие выражение, предоставляют упрощенный синтаксис для поддержки такого варианта использования.</span><span class="sxs-lookup"><span data-stu-id="98f64-113">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="98f64-114">Начиная с версии C# 6, доступные только для чтения индексаторы можно реализовать в виде члена, воплощающего выражение, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="98f64-114">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="98f64-115">Обратите внимание, что `=>` представляет тело выражения, а ключевое слово `get` не используется.</span><span class="sxs-lookup"><span data-stu-id="98f64-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span>

<span data-ttu-id="98f64-116">Начиная с версии C# 7.0, методы доступа get и set можно реализовывать в виде членов с телом в виде выражения.</span><span class="sxs-lookup"><span data-stu-id="98f64-116">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="98f64-117">В этом случае необходимо указывать оба ключевых слова (`get` и `set`).</span><span class="sxs-lookup"><span data-stu-id="98f64-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="98f64-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="98f64-118">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="98f64-119">Общие сведения об индексаторах</span><span class="sxs-lookup"><span data-stu-id="98f64-119">Indexers Overview</span></span>  
  
- <span data-ttu-id="98f64-120">Индексаторы позволяют индексировать объекты так же, как и массивы.</span><span class="sxs-lookup"><span data-stu-id="98f64-120">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="98f64-121">Метод доступа `get` возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="98f64-121">A `get` accessor returns a value.</span></span> <span data-ttu-id="98f64-122">Метод доступа `set` назначает значение.</span><span class="sxs-lookup"><span data-stu-id="98f64-122">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="98f64-123">Ключевое слово [this](../../language-reference/keywords/this.md) используется для определения индексаторов.</span><span class="sxs-lookup"><span data-stu-id="98f64-123">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="98f64-124">Ключевое слово [value`set` используется для определения значения, присваиваемого индексатором ](../../language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="98f64-124">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
- <span data-ttu-id="98f64-125">Индексаторы не нужно индексировать по целому значению; пользователь может определить конкретный механизм поиска на свое усмотрение.</span><span class="sxs-lookup"><span data-stu-id="98f64-125">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="98f64-126">Индексаторы могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="98f64-126">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="98f64-127">Индексаторы могут иметь более одного формального параметра, например при доступе к двумерному массиву.</span><span class="sxs-lookup"><span data-stu-id="98f64-127">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> <span data-ttu-id="98f64-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="98f64-128">Related Sections</span></span>  
  
- [<span data-ttu-id="98f64-129">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="98f64-129">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="98f64-130">Индексаторы в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="98f64-130">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="98f64-131">Сравнение свойств и индексаторов</span><span class="sxs-lookup"><span data-stu-id="98f64-131">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="98f64-132">Ограничение доступности методов доступа</span><span class="sxs-lookup"><span data-stu-id="98f64-132">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="98f64-133">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="98f64-133">C# Language Specification</span></span>  

<span data-ttu-id="98f64-134">Дополнительные сведения см. в разделе [Индексаторы](~/_csharplang/spec/classes.md#indexers) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="98f64-134">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="98f64-135">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="98f64-135">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="98f64-136">См. также</span><span class="sxs-lookup"><span data-stu-id="98f64-136">See also</span></span>

- [<span data-ttu-id="98f64-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="98f64-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="98f64-138">Свойства</span><span class="sxs-lookup"><span data-stu-id="98f64-138">Properties</span></span>](../classes-and-structs/properties.md)
