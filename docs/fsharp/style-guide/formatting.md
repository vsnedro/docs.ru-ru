---
title: Рекомендации по форматированию кода F#
description: Изучите рекомендации по форматированию кода F.
ms.date: 11/04/2019
ms.openlocfilehash: 2086b515b8ec9b69a44e2e65ca06fb320670dff2
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278942"
---
# <a name="f-code-formatting-guidelines"></a>Рекомендации по форматированию кода F#

В этой статье предлагаются рекомендации по форматированию кода таким образом, чтобы ваш код F-кода был:

* Как правило, рассматривается как более разборчивый
* Соответствует конвенциям, применяемым путем форматирования инструментов в Visual Studio и других редакторах
* Похож на другой код онлайн

Эти руководящие принципы основаны на [всеобъемлющем руководстве по Конвенциям о формировании F'](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Общие правила для отступов

По умолчанию используется значительное белое пространство. Следующие руководящие принципы призваны дать рекомендации относительно того, как жонглировать некоторыми проблемами, которые это может навязать.

### <a name="using-spaces"></a>Использование пробелов

При необходимости отступа необходимо использовать пробелы, а не вкладки. Требуется по крайней мере одно пространство. Организация может создавать стандарты кодирования для указания количества пробелов, которые можно использовать для отступов; два, три или четыре пробела отступов на каждом уровне, где происходит отступ, является типичным.

**Мы рекомендуем 4 места на отступ.**

Тем не менее, отступы программ является субъективным вопросом. Вариации в порядке, но первое правило, вы должны следовать это *последовательность отступов.* Выберите общепринятый стиль отступов и систематически используйте его по всей кодовой базе.

## <a name="formatting-white-space"></a>Форматирование белого пространства

ФЗ является белым пространством чувствительны. Хотя большинство семантики из белого пространства покрыты надлежащей отступы, Есть некоторые другие вещи, чтобы рассмотреть.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Форматирование операторов в арифметических выражениях

Всегда используйте белое пространство вокруг бинарных арифметических выражений:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Неунарные `-` операторы должны всегда иметь значение, они отрицают сразу же следовать:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Добавление белого пространства символ `-` после оператора может привести к путанице для других.

Таким образом, важно всегда:

* Окружать бинарные операторы с белым пространством
* Никогда не имеют задней белое пространство после необезвиднятого оператора

Особенно важно ерелита бинарного оператора арифметики. Неспособность окружить `-` двоичного оператора, в сочетании с определенными вариантами `-`форматирования, может привести к интерпретации его как unary .

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Окружите пользовательское определение оператора белым пространством

Всегда используйте белое пространство, чтобы окружить определение оператора:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Для любого пользовательского `*` оператора, который начинается с и который имеет более одного символа, необходимо добавить белое пространство в начале определения, чтобы избежать двусмысленности компилятора. Поэтому мы рекомендуем просто окружить определения всех операторов одним бело-космическим символом.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Сострелка параметра объемной функции с белым пространством

При определении подписи функции используйте `->` белое пространство вокруг символа:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Аргументы функции окружения с белым пространством

При определении функции используйте белое пространство вокруг каждого аргумента.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a>Место параметров на новой строке для очень длинных определений членов

Если у вас очень длинное определение участника, поместите параметры на новые строки и отодвините их в одну область.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

Это также относится к конструкторам:

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>Введите аннотации

#### <a name="right-pad-function-argument-type-annotations"></a>Аннотации типа типа типа функции правой панели

При определении аргументов с аннотациями типа `:` используйте белое пространство после символа:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Аннотации типа surround возврата с белым пространством

В аннотации типа let-bound или типе значения (тип возврата в случае функции) используйте белое пространство до и после символа: `:`

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>Форматирование пустых линий

* Отдельные определения функции верхнего уровня и класса с двумя пустыми строками.
* Определения метода внутри класса разделены одной пустой строкой.
* Дополнительные пустые строки могут быть использованы (экономно) для разделения групп связанных функций. Пустые линии могут быть опущены между кучей связанных однострочников (например, набор фиктивных реализаций).
* Используйте пустые строки в функциях, экономно, чтобы указать логические разделы.

## <a name="formatting-comments"></a>Форматирование комментариев

Как правило, предпочитают несколько двойных слэш комментарии по ML-стиль блок-комментариев.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

В строке комментарии должны капитализировать первое письмо.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Соглашения об именах

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Используйте верблюжьики для значений и функций, связанных с классом, связанных с ими и шаблонных

Это является общим и принятым стилем F' для использования camelCase для всех имен, связанных как локальные переменные или в шаблонных совпадений и определениях функций.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Функции локального связанного в классах должны также использовать camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Используйте верблюжьики для общественных функций, привязанных к модулю

Когда функция, связанная с модулем, является частью общедоступного API, она должна использовать camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Используйте camelCase для внутренних и частных значений и функций, связанных с модулем

Используйте camelCase для значений, связанных с частными модулем, включая следующие:

* Специальные функции в сценариях

* Значения, составляющие внутреннюю реализацию модуля или типа

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Используйте верблюжьики для параметров

Все параметры должны использовать camelCase в соответствии с конвенциями именования .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Используйте PascalCase для модулей

Все модули (верхний уровень, внутренний, частный, вложенный) должны использовать PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Используйте PascalCase для типовых деклараций, участников и меток

Классы, интерфейсы, структуры, перечисления, делегаты, записи и дискриминируемые союзы должны быть названы паскалькейсом. Члены типов и меток для записей и дискриминируемых союзов должны также использовать PascalCase.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Используйте PascalCase для конструкций, присущих .NET

Пространства имен, исключения, события и`.dll` названия/имена также должны использовать PascalCase. Это не только делает потребление из других языков .NET более естественным для потребителей, но и согласуется с соглашениями о наименовании .NET, с которыми вы, вероятно, столкнетесь.

### <a name="avoid-underscores-in-names"></a>Избегайте подчеркнутов в именах

Исторически сложилось так, что некоторые библиотеки F'а использовали подчеркивание в именах. Однако это уже не является широко признанным, отчасти потому, что это противоречит конвенциям именования .NET. Тем не менее, некоторые программисты F's используют в значительной степени, отчасти по историческим причинам, и терпимость и уважение имеет важное значение. Однако, имейте в виду, что стиль часто не любят другие, которые имеют выбор о том, чтобы использовать его.

Некоторые исключения включают взаимодействие с родными компонентами, где подчеркивание очень распространено.

### <a name="use-standard-f-operators"></a>Используйте стандартные операторы ФЗ

Следующие операторы определяются в стандартной библиотеке F и должны использоваться вместо определения эквивалентов. Использование этих операторов рекомендуется, поскольку он стремится сделать код более читаемым и идиоматичным. Разработчики с опытом работы на OCaml или на другом языке функционального программирования могут привыкнуть к различным идиомам. В следующем списке кратко излагаются рекомендуемые операторы F-е.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Используйте приставку синтаксис`Foo<T>`для генериков ()`T Foo`в предпочтении к postfix синтаксис ()

ФЗ наследует как постфикс ML стиль именования `int list`генерических типов (например, ), а `list<int>`также приставку .NET стиль (например, ). Предпочитаю стиль .NET, за исключением пяти конкретных типов:

1. Для списков F, используйте `int list` форму `list<int>`postfix: вместо .
2. Для опций F', используйте `int option` форму `option<int>`postfix: вместо .
3. Для опций значения F', используйте форму postfix: `int voption` вместо `voption<int>`.
4. Для массивов F-х используйте `int[]` синтаксиче, а `int array` не `array<int>`.
5. Для справочных `int ref` ячеек, использовать, а `ref<int>` не `Ref<int>`.

Для всех остальных типов используйте форму префикса.

## <a name="formatting-tuples"></a>Форматирование подобие

Мгновенное мгновение туловища должно быть скобками, а за разграничением запятых внутри должно последовать одно пространство, например: `(1, 2)`. `(x, y, z)`

Принято опускать скобки в сопоставлении шаблонов:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

Также принято опускать скобки, если туляк является возвратным значением функции:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

Таким образом, предпочитают скобки tuple мгновенности, но при использовании tuples для сопоставления шаблона или возврата значение, считается прекрасным, чтобы избежать скобки.

## <a name="formatting-discriminated-union-declarations"></a>Форматирование дискриминированных профсоюзных деклараций

Отступ `|` в определении типа на 4 пространства:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>Форматирование дискриминируемых профсоюзов

Мгновенные дискриминированные союзы, разделенные на несколько строк, должны предоставить содержащиеся данные новой области с отступами:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Закрытие скобки также может быть на новой строке:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Форматирование записи деклараций

Отступ `{` в определении типа на 4 пространства и начать список полей на той же строке:

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

Размещение токена открытия на новой строке и маркера закрытия на новой строке предпочтительнее, если вы объявляете реализации интерфейса или участников в записи:

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>Форматирование записей

Короткие записи могут быть написаны в одной строке:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Записи, которые больше должны использовать новые линии для меток:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Размещение токена открытия на новой строке, содержимое вкладки в течение одной области, и закрытие маркера на новой линии предпочтительнее, если вы:

* Перемещение записей в коде с различными областями отступов
* Трубопроводы их в функцию

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

Те же правила применяются к элементам списка и массива.

## <a name="formatting-copy-and-update-record-expressions"></a>Форматирование выражений записей копий и обновлений

Выражение записи копирования и обновления по-прежнему является записью, поэтому применяются аналогичные рекомендации.

Короткие выражения могут поместиться на одной строке:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Более длинные выражения должны использовать новые строки:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

И, как и в руководстве записи, вы можете посвятить отдельные строки для скобки и отступ один объем справа с выражением. Обратите внимание, что в некоторых особых случаях, таких как упаковка значения с дополнительнымбезными без скобки, возможно, потребуется держать скобки на одной строке:

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>Списки и массивы форматирования

Пишите `x :: l` с пробелами вокруг `::` оператора (является`::` оператором infix, следовательно, окружен пространствами).

Список и массивы, заявленные на одной строке, должны иметь место после открытия кронштейна и перед закрытием кронштейна:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Всегда используйте по крайней мере одно пространство между двумя различными операторами, похожими на скобки. Например, оставьте пространство `[` между `{`a и a .

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

То же самое правило применяется для списков или массивов зауполей.

Списки и массивы, разделенные на несколько строк, следуют аналогичному правилу, как и записи:

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

И как с записями, объявление открытия и закрытия скобки на их собственной линии сделает перемещение кода вокруг и трубопроводов в функции легче.

При создании массивов и списков `->` программно, предпочитают, `do ... yield` когда значение всегда генерируется:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

Более старые версии языка `yield` F's требовали указания в ситуациях, когда данные могут быть получены условно, или могут быть последовательные выражения для оценки. Предпочитаюнее опускать эти `yield` ключевые слова, если вы не должны компилировать со старой версией языка F':

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

В некоторых `do...yield` случаях, может помочь в читаемости. Эти случаи, хотя и субъективные, должны быть приняты во внимание.

## <a name="formatting-if-expressions"></a>Форматирование, если выражения

Отступы условных веществ зависят от размеров выражаемых их выражений. `cond`Если, `e1` `e2` и короткие, просто напишите их на одной строке:

```fsharp
if cond then e1 else e2
```

Если `cond`либо `e1` `e2` , или больше, но не многолинейный:

```fsharp
if cond
then e1
else e2
```

Если какое-либо из выражений является многолинейным:

```fsharp
if cond then
    e1
else
    e2
```

Несколько условных с `elif` и `else` отступом в `if`той же области, как:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Конструкции, соответствующие шаблону

Используйте `|` для каждого пункта матча без отступов. Если выражение короткое, можно рассмотреть возможность использования одной строки, если каждое подвыражение также просто.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Если выражение справа от стрелки шаблона слишком велико, переместите ее на `match` / `|`следующую строку, отступив на один шаг от .

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Шаблон сопоставления анонимных функций, начиная `function`с , как правило, не отступ слишком далеко. Например, один объем следующим образом:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Шаблон, соответствующий `let` функциям, определенным `let rec` или должны быть `let`отступом `function` 4 пространства после начала, даже если ключевое слово используется:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Мы не рекомендуем выравнивать стрелки.

## <a name="formatting-trywith-expressions"></a>Попытка форматирования/с выражениями

Шаблон, соответствующий типу исключения, должен быть `with`отступом на том же уровне, что и .

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>Применение параметра функции форматирования

Как правило, большинство приложений параметров функции выполняется на одной линии.

Если вы хотите применить параметры к функции на новой строке, отодвиньте их по одной области.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

Те же руководящие принципы применяются для выражений лямбды в качестве функциональных аргументов. Если тело выражение лямбда, тело может иметь другую линию, отступом на одну область

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

Однако, если тело выражения лямбды состоит более чем в одной строке, подумайте о том, чтобы учесть его в отдельную функцию, а не иметь многолинейную конструкцию, применяемую в качестве единого аргумента к функции.

### <a name="formatting-infix-operators"></a>Форматирование операторов infix

Отдельные операторы по пространствам. Очевидными исключениями из `!` этого `.` правила являются и операторы.

Выражения Infix ок для линейки на той же колонке:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Форматирование операторов трубопроводов

Операторы трубопроводов `|>` должны идти под выражения, на которых они работают.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>Модули форматирования

Код в локальном модуле должен быть отступом относительно модуля, но код в модуле верхнего уровня не должен быть отступом. Элементы пространства имен не должны быть отступом.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Форматирование выражений и интерфейсов объектов

Выражения и интерфейсы объектов должны быть выровнены таким же образом, чтобы `member` быть отступом после 4 пробелов.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Форматирование белого пространства в выражениях

Избегайте посторонних белых пространств в выражениях F.'.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Названные аргументы также не `=`должны иметь пространство, окружающее:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Характеристики форматирования

[Атрибуты](../language-reference/attributes.md) размещаются над конструкцией:

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>Формирование атрибутов по параметрам

Атрибуты также могут быть местами по параметрам. В этом случае поместите затем на ту же строку, что и параметр, и перед именем:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Формирование нескольких атрибутов

Когда несколько атрибутов применяются к конструкции, которая не является параметром, они должны быть размещены таким образом, что есть один атрибут на строку:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

При применении к параметру они должны находиться `;` на одной линии и отделяться от сепаратора.

## <a name="formatting-literals"></a>Форматирование буквальных

[Буквальные буквы F',](../language-reference/literals.md) использующие `Literal` атрибут, должны размещать атрибут на своей собственной линии и использовать именования PascalCase:

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Избегайте размещения атрибута на той же строке, что и значение.
