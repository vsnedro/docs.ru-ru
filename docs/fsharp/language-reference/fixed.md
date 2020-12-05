---
title: Ключевое слово fixed
description: 'Узнайте, как можно закрепить локальную систему в стеке, чтобы предотвратить сбор с помощью ключевого слова F # fixed.'
ms.date: 08/15/2020
ms.openlocfilehash: b4b0d1ae101d5f7b65bff80fa070c9fd54de8d66
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740358"
---
# <a name="the-fixed-keyword"></a>Ключевое слово fixed

`fixed`Ключевое слово позволяет «закрепить» локальную систему в стеке, чтобы предотвратить их сбор или перемещение во время сборки мусора.  Он используется для сценариев низкого уровня программирования.

## <a name="syntax"></a>Синтаксис

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Remarks

Это расширяет синтаксис выражений, позволяя извлекать указатель и привязать его к имени, которое не может быть собрано или перемещено во время сбора мусора.  

Указатель из выражения фиксируется с помощью `fixed` ключевого слова и привязывается к идентификатору с помощью `use` ключевого слова.  Семантика этого объекта аналогична управлению ресурсами с помощью `use` ключевого слова.  Указатель фиксирован, пока находится в области видимости, и, когда он выходит за пределы области, он больше не является фиксированным.  `fixed` не может использоваться вне контекста `use` привязки.  Необходимо привязать указатель к имени с помощью `use` .

Использование метода `fixed` должно выполняться в выражении в функции или в методе.  Его нельзя использовать в области действия уровня скрипта или модуля.

Как и все коды указателей, это незащищенная функция, которая выдает предупреждение при использовании.

## <a name="example"></a>Пример

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn $"pnt before - X: %d{pnt.X} Y: %d{pnt.Y}" // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn $"pnt after - X: %d{pnt.X} Y: %d{pnt.Y}" // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a>См. также

- [Модуль NativePtr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-nativeinterop-nativeptrmodule.html)
