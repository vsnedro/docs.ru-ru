---
title: Справочник по C#. Оператор delegate
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 33c438b88f1e993f4648786da9b20b91961b7ee1
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062994"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="29d9c-102">Справочник по C#. Оператор delegate</span><span class="sxs-lookup"><span data-stu-id="29d9c-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="29d9c-103">Оператор `delegate` создает анонимный метод, который можно преобразовать в тип делегата:</span><span class="sxs-lookup"><span data-stu-id="29d9c-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="29d9c-104">Начиная с C# 3, лямбда-выражения позволяют быстрее и проще создавать анонимные функции.</span><span class="sxs-lookup"><span data-stu-id="29d9c-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="29d9c-105">С помощью [оператора =>](lambda-operator.md) создайте лямбда-выражение:</span><span class="sxs-lookup"><span data-stu-id="29d9c-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="29d9c-106">См. подробнее о возможностях [лямбда-выражений](lambda-expressions.md) (например, об использовании внешних переменных).</span><span class="sxs-lookup"><span data-stu-id="29d9c-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="29d9c-107">При использовании оператора `delegate` вам, возможно, нужно будет пропустить список параметров.</span><span class="sxs-lookup"><span data-stu-id="29d9c-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="29d9c-108">В таком случае созданный анонимный метод можно будет преобразовать в тип делегата с любым списком параметров, как показано в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="29d9c-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="29d9c-109">Это единственная функция анонимных методов, которая не поддерживается лямбда-выражениями.</span><span class="sxs-lookup"><span data-stu-id="29d9c-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="29d9c-110">Во всех остальных случаях лямбда-выражение является предпочтительным способом написания встроенного кода.</span><span class="sxs-lookup"><span data-stu-id="29d9c-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="29d9c-111">Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="29d9c-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="29d9c-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="29d9c-112">C# language specification</span></span>

<span data-ttu-id="29d9c-113">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="29d9c-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="29d9c-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29d9c-114">See also</span></span>

- [<span data-ttu-id="29d9c-115">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="29d9c-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="29d9c-116">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="29d9c-116">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="29d9c-117">=> оператор</span><span class="sxs-lookup"><span data-stu-id="29d9c-117">=> operator</span></span>](lambda-operator.md)
