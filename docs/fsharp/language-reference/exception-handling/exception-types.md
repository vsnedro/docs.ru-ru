---
title: Типы исключения
description: 'Узнайте, как определять и использовать типы исключений F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557233"
---
# <a name="exception-types"></a><span data-ttu-id="ddc00-103">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="ddc00-103">Exception Types</span></span>

<span data-ttu-id="ddc00-104">В F # существуют две категории исключений: типы исключений .NET и типы исключений F #.</span><span class="sxs-lookup"><span data-stu-id="ddc00-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="ddc00-105">В этом разделе описывается определение и использование типов исключений F #.</span><span class="sxs-lookup"><span data-stu-id="ddc00-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="ddc00-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddc00-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="ddc00-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ddc00-107">Remarks</span></span>

<span data-ttu-id="ddc00-108">В предыдущем синтаксисе *Exception-Type* — это имя нового типа исключения F #, а *тип Argument —* тип аргумента, который может быть указан при вызове исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="ddc00-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="ddc00-109">Можно указать несколько аргументов с помощью типа кортежа для *типа аргумента*.</span><span class="sxs-lookup"><span data-stu-id="ddc00-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="ddc00-110">Типичное определение исключения F # напоминает следующее.</span><span class="sxs-lookup"><span data-stu-id="ddc00-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="ddc00-111">Исключение этого типа можно создать с помощью `raise` функции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ddc00-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="ddc00-112">Тип исключения F # можно использовать непосредственно в фильтрах в `try...with` выражении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ddc00-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="ddc00-113">Тип исключения, определяемый с помощью `exception` ключевого слова в F #, является новым типом, наследуемым от `System.Exception` .</span><span class="sxs-lookup"><span data-stu-id="ddc00-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddc00-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ddc00-114">See also</span></span>

- [<span data-ttu-id="ddc00-115">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="ddc00-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="ddc00-116">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="ddc00-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="ddc00-117">Иерархия исключений</span><span class="sxs-lookup"><span data-stu-id="ddc00-117">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
