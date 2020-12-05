---
title: Выражения объекта
description: 'Узнайте, как использовать выражения объекта F #, если нужно избежать дополнительного кода и издержек, необходимых для создания нового именованного типа.'
ms.date: 02/08/2019
ms.openlocfilehash: 8a3e40b7833b551eefb95ec62b935acd1ba7b1f9
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740306"
---
# <a name="object-expressions"></a>Выражения объекта

*Выражение объекта* — это выражение, которое создает новый экземпляр динамически созданного анонимного типа объекта, основанного на существующем базовом типе, интерфейсе или наборе интерфейсов.

## <a name="syntax"></a>Синтаксис

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Remarks

В предыдущем синтаксисе *TypeName* представляет существующий тип класса или тип интерфейса. *type-params* описывает необязательные параметры универсального типа. *Аргументы* используются только для типов классов, для которых требуются параметры конструктора. *Определения членов* — это переопределения методов базового класса или реализации абстрактных методов из базового класса или интерфейса.

В следующем примере показаны несколько различных типов выражений объекта.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn $"{obj1}"

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>Использование выражений объектов

Выражения объектов используются, если нужно избежать дополнительного кода и издержек, необходимых для создания нового именованного типа. При использовании выражений объектов для уменьшения числа типов, созданных в программе, можно уменьшить число строк кода и предотвратить ненужные возможности распространения типов. Вместо того чтобы создавать много типов только для обработки конкретных ситуаций, можно использовать объектное выражение, которое настраивает существующий тип или предоставляет соответствующую реализацию интерфейса для конкретного случая.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
