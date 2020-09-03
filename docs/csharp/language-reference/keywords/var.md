---
description: var. Справочник по C#
title: var. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: 303a880a54a79e50515060e0ea28e8d021fa1b76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141716"
---
# <a name="var-c-reference"></a><span data-ttu-id="ecd0b-103">var (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ecd0b-103">var (C# Reference)</span></span>

<span data-ttu-id="ecd0b-104">Начиная с Visual C# 3.0, переменные, объявленные в области действия метода, получают неявный "тип" `var`.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-104">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="ecd0b-105">Неявно типизированные локальные переменные является строго типизированными, как если бы вы объявили тип самостоятельно, однако его определяет компилятор.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="ecd0b-106">Следующие два объявления `i` функционально эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="ecd0b-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="ecd0b-107">Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Связи типов в операциях запроса LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ecd0b-107">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecd0b-108">При использовании `var` с включенными ссылочными типами, допускающими значение NULL, всегда подразумевается ссылочный тип, допускающий значение NULL, даже если тип выражения не допускает значения NULL.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-108">When `var` is used with nullable reference types enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

## <a name="example"></a><span data-ttu-id="ecd0b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="ecd0b-109">Example</span></span>

<span data-ttu-id="ecd0b-110">В следующем примере показаны два выражения запросов.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-110">The following example shows two query expressions.</span></span> <span data-ttu-id="ecd0b-111">В первом выражении использование `var` разрешено, но не является обязательным, поскольку тип результата запроса может быть задан явно как `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-111">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="ecd0b-112">Однако во втором выражении благодаря `var` результат может быть коллекцией анонимных типов, и имя этого типа доступно только для компилятора.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-112">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="ecd0b-113">Использование `var` делает создание нового класса для результата необязательным.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-113">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="ecd0b-114">Обратите внимание на то, что во втором примере переменная итерации `foreach``item` также типизирована неявно.</span><span class="sxs-lookup"><span data-stu-id="ecd0b-114">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="ecd0b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ecd0b-115">See also</span></span>

- [<span data-ttu-id="ecd0b-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ecd0b-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ecd0b-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ecd0b-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ecd0b-118">Неявно типизированные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="ecd0b-118">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
