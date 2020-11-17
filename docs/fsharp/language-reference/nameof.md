---
title: Название
description: Сведения об операторе NameOf — функции метапрограммирование, которая позволяет создавать имя любого символа в исходном коде.
ms.date: 11/12/2020
ms.openlocfilehash: 9947d7172d1b73db5c181297ec8b1131382e1f5e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688640"
---
# <a name="nameof"></a><span data-ttu-id="7c83c-103">Название</span><span class="sxs-lookup"><span data-stu-id="7c83c-103">Nameof</span></span>

<span data-ttu-id="7c83c-104">`nameof`Выражение создает строковую константу, совпадающую с именем в источнике практически для любой конструкции F # в источнике.</span><span class="sxs-lookup"><span data-stu-id="7c83c-104">The `nameof` expression produces a string constant that matches the name in source for nearly any F# construct in source.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c83c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c83c-105">Syntax</span></span>

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a><span data-ttu-id="7c83c-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c83c-106">Remarks</span></span>

<span data-ttu-id="7c83c-107">`nameof` работает путем разрешения переданного в него символа и создает имя этого символа в том виде, в котором оно объявлено в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="7c83c-107">`nameof` works by resolving the symbol passed to it and produces the name of that symbol as it is declared in your source code.</span></span> <span data-ttu-id="7c83c-108">Это полезно в различных сценариях, таких как ведение журнала, и защита ведения журнала от изменений в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="7c83c-108">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) ($"Value passed in was %d{month}.")

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="7c83c-109">Последняя строка выдаст исключение и `"month"` будет отображаться в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7c83c-109">The last line will throw an exception and `"month"` will be shown in the error message.</span></span>

<span data-ttu-id="7c83c-110">Вы можете задействовать почти каждую конструкцию F #:</span><span class="sxs-lookup"><span data-stu-id="7c83c-110">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

<span data-ttu-id="7c83c-111">`nameof` не является функцией первого класса и не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="7c83c-111">`nameof` is not a first-class function and cannot be used as such.</span></span> <span data-ttu-id="7c83c-112">Это означает, что он не может быть частично применен, и значения нельзя передать в него с помощью операторов конвейера F #.</span><span class="sxs-lookup"><span data-stu-id="7c83c-112">That means it cannot be partially applied and values cannot be piped into it via F# pipeline operators.</span></span>

## <a name="nameof-on-operators"></a><span data-ttu-id="7c83c-113">NameOf в операторах</span><span class="sxs-lookup"><span data-stu-id="7c83c-113">Nameof on operators</span></span>

<span data-ttu-id="7c83c-114">Операторы в F # можно использовать двумя способами: в качестве самого текста оператора или символа, представляющего скомпилированную форму.</span><span class="sxs-lookup"><span data-stu-id="7c83c-114">Operators in F# can be used in two ways, as an operator text itself, or a symbol representing the compiled form.</span></span> <span data-ttu-id="7c83c-115">`nameof` в операторе будет выдавать имя оператора, как оно объявлено в источнике.</span><span class="sxs-lookup"><span data-stu-id="7c83c-115">`nameof` on an operator will produce the name of the operator as it is declared in source.</span></span> <span data-ttu-id="7c83c-116">Чтобы получить скомпилированное имя, используйте скомпилированное имя в источнике:</span><span class="sxs-lookup"><span data-stu-id="7c83c-116">To get the compiled name, use the compiled name in source:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a><span data-ttu-id="7c83c-117">NameOf в универсальных шаблонах</span><span class="sxs-lookup"><span data-stu-id="7c83c-117">Nameof on generics</span></span>

<span data-ttu-id="7c83c-118">Можно также использовать имя параметра универсального типа, но синтаксис отличается:</span><span class="sxs-lookup"><span data-stu-id="7c83c-118">You can also take a name of a generic type parameter, but the syntax is different:</span></span>

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

<span data-ttu-id="7c83c-119">`nameof<'TGeneric>` принимает имя символа, как определено в источнике, а не имя типа, заменяемого в месте вызова.</span><span class="sxs-lookup"><span data-stu-id="7c83c-119">`nameof<'TGeneric>` will take the name of the symbol as defined in source, not the name of the type substituted at a call site.</span></span>

<span data-ttu-id="7c83c-120">Причина, по которой синтаксис отличается, заключается в согласовании с другими внутренними операторами F #, такими как `typeof<>` и `typedefof<>` .</span><span class="sxs-lookup"><span data-stu-id="7c83c-120">The reason why the syntax is different is to align with other F# intrinsic operators like `typeof<>` and `typedefof<>`.</span></span> <span data-ttu-id="7c83c-121">Это делает F # совместимым с операторами, которые работают с универсальными типами и что-то еще в источнике.</span><span class="sxs-lookup"><span data-stu-id="7c83c-121">This makes F# consistent with respect to operators that act on generic types and anything else in source.</span></span>

## <a name="nameof-in-pattern-matching"></a><span data-ttu-id="7c83c-122">NameOf в сопоставлении шаблонов</span><span class="sxs-lookup"><span data-stu-id="7c83c-122">Nameof in pattern matching</span></span>

<span data-ttu-id="7c83c-123">[ `nameof` Шаблон](pattern-matching.md#nameof-pattern) позволяет использовать `nameof` в выражении соответствия шаблону следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c83c-123">The [`nameof` pattern](pattern-matching.md#nameof-pattern) lets you use `nameof` in a pattern match expression like so:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
