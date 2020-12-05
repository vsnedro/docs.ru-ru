---
title: Результаты
description: 'Узнайте, как использовать тип "Result" F #, чтобы упростить написание кода, поддерживающего ошибку.'
ms.date: 08/13/2020
ms.openlocfilehash: 53b1db0c9224ae032d58c06cd3c58e3dbed03f7b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740228"
---
# <a name="results"></a>Результаты

Этот `Result<'T,'TFailure>` тип позволяет написать код, который можно составить с помощью ошибок.

## <a name="syntax"></a>Синтаксис

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>Remarks

См [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) . модуль для встроенных блоков объединения для `Result` . Java.

Обратите внимание, что тип результата является [размеченное объединением структуры](discriminated-unions.md#struct-discriminated-unions). Семантика структурного равенства применяется здесь.

`Result`Тип обычно используется в собственной обработке ошибок, которую часто называют [раилвай-ориентированным программированием](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) в сообществе F #.  Следующий тривиальный пример демонстрирует этот подход.

```fsharp
// Define a simple type which has fields that can be validated
type Request =
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() =
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn $"My request was valid! Name: {req.Name} Email {req.Email}"  
    | Error e -> printfn $"Error: {e}"
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn $"My request was valid! Name: {req.Name} Email {req.Email}"  
    | Error e -> printfn $"Error: {e}"
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

Как видите, в цепочку можно легко объединить различные функции проверки, если все они будут возвращать `Result` .  Это позволяет разбивать такие функциональные возможности на небольшие части, которые являются взаимокомпозициями по мере необходимости.  Это также имеет добавленное *значение применения* [сопоставления шаблонов](pattern-matching.md) в конце круга проверки, что в свою сторону принуждает к более высокой степени правильности программы.

## <a name="see-also"></a>См. также

- [Размеченные объединения](discriminated-unions.md)
- [Соответствие шаблону](pattern-matching.md)
