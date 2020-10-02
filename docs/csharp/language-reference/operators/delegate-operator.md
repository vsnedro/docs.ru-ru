---
description: Справочник по C#. Оператор delegate
title: Справочник по C#. Оператор delegate
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247661"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="d7e07-103">Справочник по C#. Оператор delegate</span><span class="sxs-lookup"><span data-stu-id="d7e07-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="d7e07-104">Оператор `delegate` создает анонимный метод, который можно преобразовать в тип делегата:</span><span class="sxs-lookup"><span data-stu-id="d7e07-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="d7e07-105">Начиная с C# 3, лямбда-выражения позволяют быстрее и проще создавать анонимные функции.</span><span class="sxs-lookup"><span data-stu-id="d7e07-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="d7e07-106">С помощью [оператора =>](lambda-operator.md) создайте лямбда-выражение:</span><span class="sxs-lookup"><span data-stu-id="d7e07-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="d7e07-107">См. подробнее о возможностях [лямбда-выражений](lambda-expressions.md) (например, об использовании внешних переменных).</span><span class="sxs-lookup"><span data-stu-id="d7e07-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="d7e07-108">При использовании оператора `delegate` вам, возможно, нужно будет пропустить список параметров.</span><span class="sxs-lookup"><span data-stu-id="d7e07-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="d7e07-109">В таком случае созданный анонимный метод можно будет преобразовать в тип делегата с любым списком параметров, как показано в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="d7e07-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="d7e07-110">Это единственная функция анонимных методов, которая не поддерживается лямбда-выражениями.</span><span class="sxs-lookup"><span data-stu-id="d7e07-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="d7e07-111">Во всех остальных случаях лямбда-выражение является предпочтительным способом написания встроенного кода.</span><span class="sxs-lookup"><span data-stu-id="d7e07-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="d7e07-112">Начиная с C# 9.0, можно использовать [отмены](../../discards.md), чтобы указать два или более входных параметра анонимного метода, которые не используются методом:</span><span class="sxs-lookup"><span data-stu-id="d7e07-112">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of an anonymous method that aren't used by the method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

<span data-ttu-id="d7e07-113">Если только один параметр имеет имя `_`, для обеспечения обратной совместимости `_` рассматривается как имя этого параметра в анонимном методе.</span><span class="sxs-lookup"><span data-stu-id="d7e07-113">For backwards compatibility, if only a single parameter is named `_`, `_` is treated as the name of that parameter within an anonymous method.</span></span>

<span data-ttu-id="d7e07-114">Кроме того, начиная с C# 9.0 можно использовать модификатор `static` в объявлении анонимного метода:</span><span class="sxs-lookup"><span data-stu-id="d7e07-114">Also beginning with C# 9.0, you can use the `static` modifier at the declaration of an anonymous method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

<span data-ttu-id="d7e07-115">Статический анонимный метод не может записывать локальные переменные или состояние экземпляра из охватывающих областей.</span><span class="sxs-lookup"><span data-stu-id="d7e07-115">A static anonymous method can't capture local variables or instance state from enclosing scopes.</span></span>

<span data-ttu-id="d7e07-116">Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="d7e07-116">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d7e07-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d7e07-117">C# language specification</span></span>

<span data-ttu-id="d7e07-118">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d7e07-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7e07-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d7e07-119">See also</span></span>

- [<span data-ttu-id="d7e07-120">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d7e07-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d7e07-121">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="d7e07-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="d7e07-122">=> оператор</span><span class="sxs-lookup"><span data-stu-id="d7e07-122">=> operator</span></span>](lambda-operator.md)
