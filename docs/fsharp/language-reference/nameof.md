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
# <a name="nameof"></a>Название

`nameof`Выражение создает строковую константу, совпадающую с именем в источнике практически для любой конструкции F # в источнике.

## <a name="syntax"></a>Синтаксис

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a>Remarks

`nameof` работает путем разрешения переданного в него символа и создает имя этого символа в том виде, в котором оно объявлено в исходном коде. Это полезно в различных сценариях, таких как ведение журнала, и защита ведения журнала от изменений в исходном коде.

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

Последняя строка выдаст исключение и `"month"` будет отображаться в сообщении об ошибке.

Вы можете задействовать почти каждую конструкцию F #:

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

`nameof` не является функцией первого класса и не может использоваться. Это означает, что он не может быть частично применен, и значения нельзя передать в него с помощью операторов конвейера F #.

## <a name="nameof-on-operators"></a>NameOf в операторах

Операторы в F # можно использовать двумя способами: в качестве самого текста оператора или символа, представляющего скомпилированную форму. `nameof` в операторе будет выдавать имя оператора, как оно объявлено в источнике. Чтобы получить скомпилированное имя, используйте скомпилированное имя в источнике:

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a>NameOf в универсальных шаблонах

Можно также использовать имя параметра универсального типа, но синтаксис отличается:

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

`nameof<'TGeneric>` принимает имя символа, как определено в источнике, а не имя типа, заменяемого в месте вызова.

Причина, по которой синтаксис отличается, заключается в согласовании с другими внутренними операторами F #, такими как `typeof<>` и `typedefof<>` . Это делает F # совместимым с операторами, которые работают с универсальными типами и что-то еще в источнике.

## <a name="nameof-in-pattern-matching"></a>NameOf в сопоставлении шаблонов

[ `nameof` Шаблон](pattern-matching.md#nameof-pattern) позволяет использовать `nameof` в выражении соответствия шаблону следующим образом:

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
