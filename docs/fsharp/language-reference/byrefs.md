---
title: Byref
description: 'Сведения о типах, схожих с ByRef и ByRef, в F #, которые используются для низкоуровневого программирования.'
ms.date: 11/04/2019
ms.openlocfilehash: ff2c06d8940f7341d5d8b1d942be264bfac586c5
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740319"
---
# <a name="byrefs"></a>Byref

F # имеет две основные функциональные области, которые имеют место в пространстве низкоуровневого программирования:

* `byref` / `inref` / `outref` Типы, являющиеся управляемыми указателями. Они имеют ограничения на использование, поэтому нельзя компилировать программу, недопустимую во время выполнения.
* Структура, похожая на `byref` [структуру](structures.md) , которая имеет подобную семантику и те же ограничения времени компиляции, что и `byref<'T>` . Один из примеров: <xref:System.Span%601> .

## <a name="syntax"></a>Синтаксис

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a>ByRef, инреф и аутреф

Существует три вида `byref` :

* `inref<'T>`управляемый указатель для чтения базового значения.
* `outref<'T>`управляемый указатель для записи в базовое значение.
* `byref<'T>`управляемый указатель для чтения и записи базового значения.

`byref<'T>`Может быть передан, где `inref<'T>` ожидается. Аналогичным образом `byref<'T>` можно передать значение, где `outref<'T>` ожидается.

## <a name="using-byrefs"></a>Использование ByRef

Чтобы использовать `inref<'T>` , необходимо получить значение указателя с помощью `&` :

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn $"Now: %O{dt}"

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Для записи в указатель с помощью `outref<'T>` или `byref<'T>` необходимо также сделать значение, которое вы захватите на указатель `mutable` .

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn $"Now: %O{dt}"
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

Если вы пишете только указатель, а не читаете его, рассмотрите возможность использования `outref<'T>` вместо `byref<'T>` .

### <a name="inref-semantics"></a>Семантика инреф

Рассмотрим следующий код:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

В семантическом виде это означает следующее:

* Владелец `x` указателя может использовать его только для чтения значения.
* Любой указатель, полученный к `struct` полям, вложенным в `SomeStruct` , задается типом `inref<_>` .

Также верно следующее:

* Нет никаких последствие того, что другие потоки или псевдонимы не имеют доступа на запись `x` .
* Неизменность не является `SomeStruct` неизменяемой, так как является `x` `inref` .

Однако для типов значений F #, которые **являются** неизменяемыми, `this` указатель выводится как `inref` .

Все эти правила вместе означают, что владелец `inref` указателя не может изменить немедленное содержимое памяти, на которое указывает.

### <a name="outref-semantics"></a>Семантика аутреф

Целью `outref<'T>` является указание на то, что указатель должен быть записан только в. Неожиданно, `outref<'T>` позволяет считывать базовое значение, несмотря на его имя. Это происходит в целях совместимости. Семантически, не `outref<'T>` отличается от `byref<'T>` .

### <a name="interop-with-c"></a>Взаимодействие с C\#

C# поддерживает `in ref` `out ref` Ключевые слова и, а также `ref` возвращает. В следующей таблице показано, как F # интерпретирует вырожденные выпуски C#:

|Конструкция C#|Выводит F #|
|------------|---------|
|`ref` Возвращаемое значение|`outref<'T>`|
|`ref readonly` Возвращаемое значение|`inref<'T>`|
|Параметр `in ref`|`inref<'T>`|
|Параметр `out ref`|`outref<'T>`|

В следующей таблице показано, какие выпуски F #:

|Конструкция F #|Выпущенная конструкция|
|------------|-----------------|
|Аргумент `inref<'T>`|`[In]` атрибут в аргументе|
|`inref<'T>` вернул|`modreq` атрибут для значения|
|`inref<'T>` в абстрактном слоте или реализации|`modreq` аргумент ON или Return|
|Аргумент `outref<'T>`|`[Out]` атрибут в аргументе|

### <a name="type-inference-and-overloading-rules"></a>Определение типа и перегрузка правил

`inref<'T>`Тип выводится компилятором F # в следующих случаях:

1. Параметр или возвращаемый тип .NET, имеющий `IsReadOnly` атрибут.
2. `this`Указатель на тип структуры, не имеющий изменяемых полей.
3. Адрес области памяти, полученной из другого `inref<_>` указателя.

Когда выполняется неявный адрес `inref` , перегрузка с аргументом типа `SomeType` является предпочтительной для перегрузки с аргументом типа `inref<SomeType>` . Пример:

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

В обоих случаях перегрузки `System.DateTime` разрешаются, а не перегрузками `inref<System.DateTime>` .

## <a name="byref-like-structs"></a>Структуры, аналогичные ByRef

В дополнение к `byref` / `inref` / `outref` три можно определить собственные структуры, которые могут соответствовать `byref` семантике, схожей с. Это делается с помощью <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> атрибута:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` не подразумевается `Struct` . Оба должны присутствовать в типе.

Структура " `byref` -Like" в F # является типом значения, привязанного к стеку. Он никогда не выделяется в управляемой куче. `byref`Структура, похожая на структуру, полезна для высокопроизводительного программирования, так как она применяется с набором строгих проверок на время существования и без записи. Правила:

* Их можно использовать в качестве параметров функций, параметров методов, локальных переменных, возвращаемых методом.
* Они не могут быть статическими или членами экземпляров класса или обычной структуры.
* Они не могут быть захвачены ни одной конструкцией замыкания ( `async` методами или лямбда-выражениями).
* Их нельзя использовать в качестве универсального параметра.

Последний момент является ключевым для программирования в стиле конвейера F #, как и `|>` универсальная функция, которая выполняет параметризацию входных типов. Это ограничение может быть ослаблено `|>` в будущем, так как оно встроено и не выполняет вызовы невстроенных универсальных функций в тексте.

Хотя эти правила строго ограничивают использование, они делают это для обеспечения безопасности высокопроизводительных вычислительных систем.

## <a name="byref-returns"></a>Возвраты по ссылке

Функция ByRef возвращает из функций или членов F #, которые могут быть созданы и использованы. При использовании `byref` метода, возвращающего возврат, значение неявно разыменовано. Пример:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn $"%d{squared}"
```

Чтобы получить значение ByRef, переменная, содержащая значение, должна находиться дольше текущей области.
Кроме того, чтобы вернуть ByRef, используйте `&value` (где value — переменная, которая находится дольше текущей области).

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Чтобы избежать неявного разыменования, например передачи ссылки через несколько цепочек вызовов, используйте `&x` (где `x` — это значение).

Вы также можете напрямую присвоить значение `byref` . Рассмотрим следующую (очень императивную) программу:

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn $"Original sequence: %O{c}"

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn $"New sequence:      %O{c}"

    0 // return an integer exit code
```

Результат.

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Определение области для ByRef

`let`Значение привязки не может быть больше, чем область, в которой он был определен. Например, запрещены следующие возможности:

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

Это не позволит получить разные результаты в зависимости от того, выполняется ли компиляция с оптимизацией или нет.
