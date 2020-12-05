---
title: Операторы, допускающие значение NULL
description: 'Сведения об операторах, допускающих значение null, которые доступны на языке программирования F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 9ac6afc2c3f4277ee6e93b1ccb3d21f892926b4b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740371"
---
# <a name="nullable-operators"></a>Операторы, допускающие значение NULL

Операторы, допускающие значение null, являются бинарными арифметическими или операторами сравнения, работающими с арифметическими типами, допускающими значение null, на одной Типы, допускающие значение null, часто возникают при работе с данными из таких источников, как базы данных, которые допускают значения NULL вместо фактических значений. Операторы, допускающие значения NULL, часто используются в выражениях запросов. В дополнение к операторам, допускающим значения NULL для арифметических операций и сравнения, операторы преобразования можно использовать для преобразования между типами, допускающими значение null. Кроме того, существуют версии определенных операторов запросов, допускающие значения NULL.

## <a name="table-of-nullable-operators"></a>Таблица операторов, допускающих значения NULL

В следующей таблице перечислены операторы Nullable, поддерживаемые в языке F #.

|Nullable по левому краю|Допускает значения NULL справа|Обе стороны допускают значения NULL|
|---|---|---|
|[? >=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=%20))|[>=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E=?%20))|[? >=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=?%20))|
|[? >](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E%20))|[>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E?%20))|[? >?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E?%20))|
|[? <=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=%20))|[<=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C=?%20))|[? <=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=?%20))|
|[? <](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%20))|[<?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C?%20))|[? <?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C?%20))|
|[?=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=%20))|[=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20=?%20))|[?=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=?%20))|
|[? <>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E%20))|[<>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C%3E?%20))|[? <>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E?%20))|
|[?+](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+%20))|[+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20+?%20))|[?+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+?%20))|
|[?-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-%20))|[-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20-?%20))|[?-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-?%20))|
|[?*](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*%20))|[*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20*?%20))|[?*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*?%20))|
|[?/](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/%20))|[/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20/?%20))|[?/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/?%20))|
|[?%](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%%20))|[%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%?%20))|[?%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%?%20))|

## <a name="remarks"></a>Remarks

Операторы, допускающие значение null, включены в модуль [функция nullableoperators](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html) в пространстве имен [FSharp. LINQ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html). Тип данных, допускающий значение null, — `System.Nullable<'T>` .

В выражениях запросов типы, допускающие значение null, возникают при выборе данных из источника данных, который допускает значения NULL вместо значений. В SQL Server базе данных каждый столбец данных в таблице имеет атрибут, указывающий, разрешены ли значения NULL. Если разрешены значения NULL, данные, возвращаемые из базы данных, могут содержать значения NULL, которые не могут быть представлены простым типом данных, таким как `int` , `float` и т. д. Таким образом, данные возвращаются как `System.Nullable<int>` вместо `int` , а `System.Nullable<float>` вместо `float` . Фактическое значение можно получить из объекта с `System.Nullable<'T>` помощью `Value` свойства, а также определить, `System.Nullable<'T>` имеет ли объект значение, вызвав `HasValue` метод. Еще один полезный метод — `System.Nullable<'T>.GetValueOrDefault` метод, который позволяет получить значение или значение по умолчанию для соответствующего типа. Значением по умолчанию является любая форма нулевого значения, например 0, 0,0 или `false` .

Типы, допускающие значение null, могут быть преобразованы в простые типы, не допускающие значения NULL, с помощью стандартных операторов преобразования, таких как `int` или `float` . Также можно преобразовать один тип, допускающий значение null, в другой тип, допускающий значение null, с помощью операторов преобразования для типов, допускающих значение null. Соответствующие операторы преобразования имеют те же имена, что и стандартные, но они находятся в отдельном модуле, модулем, [допускающим значение NULL](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullablemodule.html) , в пространстве имен [FSharp. LINQ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html) . Как правило, это пространство имен открывается при работе с выражениями запросов. В этом случае можно использовать операторы преобразования, допускающие значения NULL, добавив префикс `Nullable.` к соответствующему оператору преобразования, как показано в следующем коде.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn $"%f{float nullableFloat}"
```

Результат выглядит так: `10.000000`.

Операторы запроса для полей данных, допускающих значения NULL, такие как `sumByNullable` , также существуют для использования в выражениях запросов. Операторы запросов для типов, не допускающих значения NULL, не совместимы с типами, допускающими значение null, поэтому при работе со значениями данных, допускающими значение null, необходимо использовать версию соответствующего оператора запроса, допускающую значение null. Дополнительные сведения см. в разделе [выражения запросов](../query-expressions.md).

В следующем примере показано использование операторов Nullable в выражении запроса F #. В первом запросе показано, как создать запрос без оператора, допускающего значение null. второй запрос показывает эквивалентный запрос, использующий оператор, допускающий значение null. Полный контекст, включая настройку базы данных для использования этого примера кода, см. в разделе [Пошаговое руководство. доступ к базе данных SQL с помощью поставщиков типов](../../tutorials/type-providers/index.md).

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn $"%d{row.TestData1.Value} %s{row.Name}")

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d{row.TestData1.GetValueOrDefault()} %s{row.Name}")
```

## <a name="see-also"></a>См. также

- [Поставщики типов](../../tutorials/type-providers/index.md)
- [Выражения запросов](../query-expressions.md)
