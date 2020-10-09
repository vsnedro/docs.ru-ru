---
description: Справочник по C#. Оператор new
title: Справочник по C#. Оператор new
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609386"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="df598-103">Оператор new (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="df598-103">new operator (C# reference)</span></span>

<span data-ttu-id="df598-104">Оператор `new` создает экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="df598-104">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="df598-105">Ключевое слово `new` можно также использовать как [модификатор объявления члена](../keywords/new-modifier.md) или [ограничение универсального типа](../keywords/new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="df598-105">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="df598-106">Вызов конструктора</span><span class="sxs-lookup"><span data-stu-id="df598-106">Constructor invocation</span></span>

<span data-ttu-id="df598-107">Для создания экземпляра типа обычно вызывается один из [конструкторов](../../programming-guide/classes-and-structs/constructors.md) этого типа с помощью оператора `new`:</span><span class="sxs-lookup"><span data-stu-id="df598-107">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

<span data-ttu-id="df598-108">Для создания экземпляра объекта и его инициализации в одном операторе можно использовать [инициализатор объекта или элементов](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) с оператором `new`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df598-108">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

<span data-ttu-id="df598-109">Начиная с версии C# 9.0 выражения вызова конструктора имеют целевой тип.</span><span class="sxs-lookup"><span data-stu-id="df598-109">Beginning with C# 9.0, constructor invocation expressions are target-typed.</span></span> <span data-ttu-id="df598-110">То есть, если известен целевой тип выражения, вы можете опустить имя типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df598-110">That is, if a target type of an expression is known, you can omit a type name, as the following example shows:</span></span>

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

<span data-ttu-id="df598-111">Как показано в предыдущем примере, выражение `new` с целевым типом всегда указывается в скобках.</span><span class="sxs-lookup"><span data-stu-id="df598-111">As the preceding example shows, you always use parentheses in a target-typed `new` expression.</span></span>

<span data-ttu-id="df598-112">Если целевой тип выражения `new` неизвестен (например, если вы используете ключевое слово [`var`](../keywords/var.md)), нужно указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="df598-112">If a target type of a `new` expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword), you must specify a type name.</span></span>

## <a name="array-creation"></a><span data-ttu-id="df598-113">создание массива</span><span class="sxs-lookup"><span data-stu-id="df598-113">Array creation</span></span>

<span data-ttu-id="df598-114">С помощью оператора `new` можно также создать экземпляр массива, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df598-114">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

<span data-ttu-id="df598-115">Чтобы создать экземпляр массива и заполнить его элементами в одном операторе, используйте синтаксис инициализации массива.</span><span class="sxs-lookup"><span data-stu-id="df598-115">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="df598-116">В следующем примере показаны различные способы сделать это:</span><span class="sxs-lookup"><span data-stu-id="df598-116">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="df598-117">Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="df598-117">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="df598-118">Создание экземпляров анонимных типов</span><span class="sxs-lookup"><span data-stu-id="df598-118">Instantiation of anonymous types</span></span>

<span data-ttu-id="df598-119">Чтобы создать экземпляр [анонимного типа](../../programming-guide/classes-and-structs/anonymous-types.md), используйте оператор `new` и синтаксис инициализации объекта:</span><span class="sxs-lookup"><span data-stu-id="df598-119">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="df598-120">Уничтожение экземпляров типа</span><span class="sxs-lookup"><span data-stu-id="df598-120">Destruction of type instances</span></span>

<span data-ttu-id="df598-121">Уничтожать ранее созданные экземпляры типа необязательно.</span><span class="sxs-lookup"><span data-stu-id="df598-121">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="df598-122">Экземпляры как ссылочных типов, так и типов значений уничтожаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="df598-122">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="df598-123">Экземпляры типов значений уничтожаются, как только уничтожается содержащий их контекст.</span><span class="sxs-lookup"><span data-stu-id="df598-123">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="df598-124">Экземпляры ссылочных типов уничтожаются [сборщиком мусора](../../../standard/garbage-collection/index.md) в неуказанное время после удаления последней ссылки на них.</span><span class="sxs-lookup"><span data-stu-id="df598-124">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at some unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="df598-125">Для экземпляров типа, которые содержат неуправляемые ресурсы, например дескриптор файла, рекомендуется использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="df598-125">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="df598-126">Дополнительные сведения см. в справке по API <xref:System.IDisposable?displayProperty=nameWithType> и статье об [операторе using](../keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="df598-126">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="df598-127">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="df598-127">Operator overloadability</span></span>

<span data-ttu-id="df598-128">Пользовательский тип не может перегружать оператор `new`.</span><span class="sxs-lookup"><span data-stu-id="df598-128">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="df598-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="df598-129">C# language specification</span></span>

<span data-ttu-id="df598-130">Дополнительные сведения см. в разделе [Оператор new](~/_csharplang/spec/expressions.md#the-new-operator)[спецификация языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="df598-130">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="df598-131">Подробные сведения о выражении `new` с целевым типом см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span><span class="sxs-lookup"><span data-stu-id="df598-131">For more information about a target-typed `new` expression, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df598-132">См. также</span><span class="sxs-lookup"><span data-stu-id="df598-132">See also</span></span>

- [<span data-ttu-id="df598-133">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="df598-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="df598-134">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="df598-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="df598-135">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="df598-135">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
