---
title: Типы значений, допускающие значение NULL
description: 'Узнайте, как использовать типы значений, допускающие значение null, способ представления типа значения, который также может иметь значение null, в F #.'
ms.date: 11/19/2020
ms.openlocfilehash: da0cd85bd651db81ba98c02a9db31d92dc52a8c6
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740434"
---
# <a name="nullable-value-types"></a>Типы значений, допускающие значение NULL

_Тип значения, допускающий значения NULL_ `Nullable<'T>` , представляет любой тип [структуры](structures.md) , который также может иметь значение `null` . Это полезно при взаимодействии с библиотеками и компонентами, которые могут представлять типы таких типов, например целые числа, со `null` значением для повышения эффективности. Базовый тип, поддерживающий эту конструкцию, — <xref:System.Nullable%601?displayProperty=nameWithType> .

## <a name="syntax"></a>Синтаксис

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a>Объявление и присваивание со значениями

Объявление типа значения, допускающего значение null, аналогично объявлению любого типа, подобного оболочке, в F #:

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

Можно также елиде параметр универсального типа и разрешить вывод типа для его разрешения:

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

Чтобы присвоить тип значения, допускающего значение null, необходимо также быть явным. Не существует неявного преобразования для определенных в F # типов значений, допускающих значения NULL:

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a>Присвоить значение null

Нельзя напрямую присвоить `null` тип значения, допускающего значение null. `Nullable()`Вместо этого используйте:

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

Это вызвано тем, что `Nullable<'T>` имеет `null` неправильное значение.

## <a name="pass-and-assign-to-members"></a>Передача и назначение членам

Основное различие между работой с членами и значениями F # заключается в том, что типы значений, допускающие значение null, могут быть неявно выведены при работе с членами. Рассмотрим метод фоллинг, принимающий тип значения Nullable в качестве входных данных:

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

В предыдущем примере можно передать `12` методу `M` . Также можно присвоить значение `12` свойству Auto `NVT` . Компилятор F # неявно преобразует вызов или такое назначение, если целевой тип соответствует входным данным, если входные данные могут быть сконструированы как тип значения нуллабел.

## <a name="examine-a-nullable-value-type-instance"></a>Проверка экземпляра типа значения, допускающего значение null

В отличие от [параметров](options.md), которые являются обобщенной конструкцией для представления возможного значения, типы значений, допускающие значение null, не используются при сопоставлении шаблонов. Вместо этого необходимо использовать [`if`](conditional-expressions-if-then-else.md) выражение и проверить `HasValue` свойство.

Чтобы получить базовое значение, используйте `Value` свойство после `HasValue` проверки, например так:

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a>Операторы, допускающие значение null

Операции с типами значений, допускающими значения NULL, такие как арифметическое или сравнение, могут потребовать использования [операторов, допускающих значение NULL](symbol-and-operator-reference/nullable-operators.md).

Можно преобразовать из одного типа значений, допускающего значение null, в другой с помощью операторов преобразования из `FSharp.Linq` пространства имен:

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

Можно также использовать соответствующий оператор, не допускающий значения NULL, для преобразования в примитивный тип, если он не имеет значения:

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

Можно также использовать операторы Nullable в качестве короткого оператора для проверки `HasValue` и `Value` :

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

`?>`Сравнение проверяет, является ли левая часть значения NULL, и только если она имеет значение. Он эквивалентен строке, следующей за ней.

## <a name="see-also"></a>См. также

- [Структуры](structures.md)
- [Параметры F #](options.md)
