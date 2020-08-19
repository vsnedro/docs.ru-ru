---
title: Массивы
description: 'Узнайте, как создавать и использовать массивы на языке программирования F #.'
ms.date: 08/13/2020
ms.openlocfilehash: 37f781ccd2c7bc2ca2c7b93bda53bbb3ea93b504
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608499"
---
# <a name="arrays"></a>Массивы

Массивы — это изменяемые коллекции последовательных элементов данных с фиксированным размером (от нуля), которые имеют один и тот же тип.

## <a name="create-arrays"></a>Создание массивов

Массивы можно создавать несколькими способами. Можно создать небольшой массив, перечисляя последовательные значения между `[|` и `|]` и разделив их точкой с запятой, как показано в следующих примерах.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

Можно также разместить каждый элемент на отдельной строке, в этом случае разделитель точкой с запятой является необязательным.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

Тип элементов массива выводится из используемых литералов и должен быть единообразным. Следующий код вызывает ошибку, поскольку 1,0 является числом с плавающей запятой и 2, а 3 — целыми числами.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

Для создания массивов также можно использовать выражения последовательности. Ниже приведен пример, создающий массив квадратов целых чисел от 1 до 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

Чтобы создать массив, в котором все элементы инициализируются нулем, используйте `Array.zeroCreate` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a>Элементы доступа

Доступ к элементам массива можно получить с помощью оператора-точки ( `.` ) и квадратных скобок ( `[` и `]` ).

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

Индексы массива начинаются с 0.

Можно также получить доступ к элементам массива с помощью нотации среза, что позволяет указать поддиапазон массива. Ниже приведены примеры нотаций среза.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

При использовании нотации среза создается новая копия массива.

## <a name="array-types-and-modules"></a>Типы массивов и модули

Тип всех массивов F # является типом .NET Framework <xref:System.Array?displayProperty=nameWithType> . Таким образом, массивы F # поддерживают все функциональные возможности, доступные в <xref:System.Array?displayProperty=nameWithType> .

[ `Array` Модуль](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) поддерживает операции с одномерные массивами. Модули `Array2D` , `Array3D` и `Array4D` содержат функции, поддерживающие операции с массивами из двух, трех и четырех измерений соответственно. Массивы с рангом более четырех можно создать с помощью <xref:System.Array?displayProperty=nameWithType> .

### <a name="simple-functions"></a>Простые функции

[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) Возвращает элемент. [`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) Задает длину массива. [`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) Задает для элемента указанное значение. В следующем примере кода показано использование этих функций.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

Выходные данные выглядят следующим образом.

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Функции, создающие массивы

Несколько функций создают массивы, не требуя наличия существующего массива. [`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) создает новый массив, который не содержит элементов. [`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) создает массив указанного размера и задает для всех элементов указанные значения. [`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) создает массив с учетом измерения и функции для создания элементов. [`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) создает массив, в котором все элементы инициализируются значением нулевого значения для типа массива. Эти функции показаны в следующем коде.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

Выходные данные выглядят следующим образом.

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) создает новый массив, содержащий элементы, скопированные из существующего массива. Обратите внимание, что копия является неполной копией, что означает, что если тип элемента является ссылочным, копируется только ссылка, а не базовый объект. Это показано в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

Результат выполнения приведенного выше кода выглядит следующим образом:

```console
[|Test1; Test2; |]
[|; Test2; |]
```

Строка `Test1` отображается только в первом массиве, так как операция создания нового элемента перезаписывает ссылку в `firstArray` , но не влияет на исходную ссылку на пустую строку, которая все еще присутствует в `secondArray` . Строка `Test2` отображается в обоих массивах, так как `Insert` операция с <xref:System.Text.StringBuilder?displayProperty=nameWithType> типом влияет на базовый <xref:System.Text.StringBuilder?displayProperty=nameWithType> объект, на который имеется ссылка в обоих массивах.

[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) создает новый массив из поддиапазона массива. Укажите поддиапазон, указав начальный индекс и длину. В следующем коде показано использование функции `Array.sub`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

Выходные данные показывают, что подмассив начинается в элементе 5 и содержит 10 элементов.

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) создает новый массив, объединяя два существующих массива.

В следующем примере кода демонстрируется **массив. append**.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) выбирает элементы массива для включения в новый массив. В следующем коде демонстрируется `Array.choose` . Обратите внимание, что тип элемента массива не обязательно должен совпадать с типом значения, возвращаемого в типе параметра. В этом примере тип элемента —, `int` а параметр — результат функции полинома, в `elem*elem - 1` виде числа с плавающей запятой.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) выполняет указанную функцию для каждого элемента массива существующего массива, а затем собирает элементы, созданные функцией, и объединяет их в новый массив. В следующем коде демонстрируется `Array.collect` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) принимает последовательность массивов и объединяет их в один массив. В следующем коде демонстрируется `Array.concat` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) принимает логическую функцию-условие и создает новый массив, содержащий только те элементы из входного массива, для которых условие имеет значение true. В следующем коде демонстрируется `Array.filter` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) создает новый массив, переменяя порядок существующего массива на другой. В следующем коде демонстрируется `Array.rev` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
"Hello world!"
```

В модуле массива можно легко объединить функции, которые преобразуют массивы с помощью конвейерного оператора ( `|>` ), как показано в следующем примере.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

Выходные данные:

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>Многомерные массивы

Можно создать многомерный массив, но для записи литерала многомерного массива нет синтаксиса. Используйте оператор, [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) чтобы создать массив из последовательности последовательностей элементов массива. Последовательности могут быть литералами массива или списка. Например, следующий код создает двумерный массив.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

Можно также использовать функцию [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) для инициализации массивов двух измерений, а аналогичные функции доступны для массивов из трех и четырех измерений. Эти функции принимают функцию, которая используется для создания элементов. Чтобы создать двумерный массив, содержащий элементы, для которых задано начальное значение вместо указания функции, используйте [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) функцию, которая также доступна для массивов, размер которых не превышает четырех. В следующем примере кода сначала показано, как создать массив массивов, содержащих нужные элементы, а затем использовать `Array2D.init` для создания требуемого двумерного массива.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

Синтаксис индексирования и среза массива поддерживается для массивов вплоть до ранга 4. При указании индекса в нескольких измерениях для разделения индексов используются запятые, как показано в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

Тип двумерного массива записывается как `<type>[,]` (например, `int[,]` , `double[,]` ), а тип трехмерного массива записывается как `<type>[,,]` , и т. д. для массивов с большими размерами.

Для многомерных массивов также доступен только подмножество функций, доступных для одномерных массивов.

### <a name="array-slicing-and-multidimensional-arrays"></a>Создание срезов массива и многомерных массивов

В двухмерном массиве (матрице) можно извлечь подматрицу, указав диапазоны и используя символ-шаблон ( `*` ) для указания целых строк или столбцов.

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

Можно разбить многомерный массив на подмассивы того же или более низкого измерения. Например, можно получить вектор из матрицы, указав одну строку или столбец.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

Этот синтаксис среза можно использовать для типов, реализующих операторы доступа к элементам и перегруженные `GetSlice` методы. Например, следующий код создает тип матрицы, который служит оболочкой для 2D-массива F #, реализует свойство Item для обеспечения поддержки индексации массива и реализует три версии `GetSlice` . Если этот код можно использовать в качестве шаблона для типов матриц, можно использовать все операции по фрагментированию, описанные в этом разделе.

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a>Логические функции в массивах

Функции [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) и [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) элементы теста в одном или двух массивах соответственно. Эти функции принимают тестовую функцию и возвращают `true` , если существует элемент (или пара элементов для `Array.exists2` ), удовлетворяющий условию.

В следующем коде демонстрируется использование `Array.exists` и `Array.exists2` . В этих примерах новые функции создаются путем применения только одного из аргументов, в таких случаях аргумент функции.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
true
false
false
true
```

Аналогичным образом функция [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) проверяет массив, чтобы определить, удовлетворяет ли каждый элемент логическому условию. Этот вариант [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) выполняет ту же функцию с помощью логической функции, включающей элементы двух массивов с одинаковой длиной. В следующем коде показано использование этих функций.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

Выходные данные для этих примеров выглядят следующим образом.

```console
false
true
true
false
```

### <a name="search-arrays"></a>Поиск по массивам

[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) принимает логическую функцию и возвращает первый элемент, для которого возвращается функция `true` , или вызывает, <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> если не найден элемент, удовлетворяющий условию. [`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) функция похожа на `Array.find` , за исключением того, что она возвращает индекс элемента, а не сам элемент.

Следующий код использует `Array.find` и `Array.findIndex` для того, чтобы узнать число, которое является как идеальным квадратом, так и идеальным кубом.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

Выходные данные выглядят следующим образом.

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) функция похожа `Array.find` на, за исключением того, что его результат является типом параметра и возвращается, `None` Если элемент не найден. `Array.tryFind` следует использовать вместо, `Array.find` Если неизвестно, находится ли соответствующий элемент в массиве. Аналогично, [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) он похож на, `Array.findIndex` за исключением того, что тип параметра является возвращаемым значением. Если элемент не найден, параметр имеет значение `None` .

В следующем коде показано использование функции `Array.tryFind`. Этот код зависит от предыдущего кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

Выходные данные выглядят следующим образом.

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

Используется [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) , если необходимо преобразовать элемент в дополнение к его поиску. Результатом является первый элемент, для которого функция возвращает преобразованный элемент в виде значения параметра или значение, `None` Если такой элемент не найден.

В следующем коде показано использование `Array.tryPick`. В этом случае вместо лямбда-выражения для упрощения кода определены несколько локальных вспомогательных функций.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

Выходные данные выглядят следующим образом.

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a>Выполнение вычислений на массивах

[`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average)Функция возвращает среднее значение каждого элемента в массиве. Ограничены типами элементов, которые поддерживают точное деление на целое число, которое включает типы с плавающей запятой, но не целочисленные типы. [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy)Функция возвращает среднее значение для результатов вызова функции для каждого элемента. Для массива целочисленного типа можно использовать `Array.averageBy` функцию и преобразовать каждый элемент в тип с плавающей запятой для вычисления.

Используйте [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) или [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) для получения максимального или минимального элемента, если тип элемента поддерживает его. Аналогично, [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) и [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) позволяет сначала выполнить функцию, например, для преобразования в тип, поддерживающий сравнение.

[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) Добавляет элементы массива и [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) вызывает функцию для каждого элемента и добавляет результаты вместе.

Чтобы выполнить функцию для каждого элемента в массиве без сохранения возвращаемых значений, используйте [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) . Для функции, включающей два массива одинаковой длины, используйте [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) . Если необходимо также разместить массив результатов функции, используйте [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) или [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) , который работает с двумя массивами за раз.

Вариации [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) и [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) позволяют индекс элемента участвовать в вычислении; то же самое справедливо [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) и для, и [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2) .

Функции [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) ,, [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) , [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) и [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) выполняют алгоритмы, которые используют все элементы массива. Аналогичным образом, вариации [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) и [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) вычисления для двух массивов.

Эти функции для выполнения вычислений соответствуют функциям с одинаковыми именами в [модуле List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html). Примеры использования см. в разделе [списки](lists.md).

### <a name="modify-arrays"></a>Изменение массивов

[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) Задает для элемента указанное значение. [`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) Задает для диапазона элементов в массиве указанное значение. В следующем коде приведен пример `Array.fill` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

Выходные данные выглядят следующим образом.

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

Можно использовать [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) для копирования подраздела одного массива в другой массив.

### <a name="convert-to-and-from-other-types"></a>Преобразование в другие типы и из других типов

[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) создает массив из списка. [`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) создает массив из последовательности. [`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) и [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) преобразуются в другие типы коллекций из типа массива.

### <a name="sort-arrays"></a>Сортировка массивов

Используйте [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) для сортировки массива с помощью универсальной функции сравнения. Используйте [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) для указания функции, которая создает значение, называемое *ключом*, для сортировки с помощью универсальной функции сравнения для ключа. Используйте [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) , если требуется предоставить пользовательскую функцию сравнения. `Array.sort`, `Array.sortBy` и `Array.sortWith` все возвращают отсортированный массив как новый массив. Варианты [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace) , [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) и [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) изменяют существующий массив вместо того, чтобы возвращать новый.

### <a name="arrays-and-tuples"></a>Массивы и кортежи

Функции [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) и [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) преобразуют массивы пар кортежей в кортежи массивов и наоборот. [`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) и [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) похожи, за исключением того, что они работают с кортежами из трех элементов или кортежей из трех массивов.

## <a name="parallel-computations-on-arrays"></a>Параллельные вычисления на массивах

Модуль [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) содержит функции для выполнения параллельных вычислений с массивами. Этот модуль недоступен в приложениях, предназначенных для версий .NET Framework до версии 4.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Типы языка F#](fsharp-types.md)
