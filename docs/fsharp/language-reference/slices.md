---
title: Срезы
description: 'Узнайте, как использовать срезы для существующих типов данных F # и как определять собственные срезы для других типов данных.'
ms.date: 12/23/2019
ms.openlocfilehash: a3920ad9e1b205b506aaee92c4606bcebf94feba
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557081"
---
# <a name="slices"></a><span data-ttu-id="b1ad5-103">Срезы</span><span class="sxs-lookup"><span data-stu-id="b1ad5-103">Slices</span></span>

<span data-ttu-id="b1ad5-104">В F # срез — это подмножество любого типа данных, имеющего `GetSlice` метод в его определении или в [расширении типа](type-extensions.md)в области.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="b1ad5-105">Чаще всего он используется с массивами и списками F #.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="b1ad5-106">В этой статье объясняется, как создавать срезы из существующих типов F # и как определять собственные срезы.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="b1ad5-107">Срезы похожи на [индексаторы](./members/indexed-properties.md), но вместо получения одного значения из базовой структуры данных они получают несколько.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="b1ad5-108">В настоящее время F # поддерживает встроенную поддержку для срезов строк, списков, массивов и двумерных массивов.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="b1ad5-109">Базовый срез с списками и массивами F #</span><span class="sxs-lookup"><span data-stu-id="b1ad5-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="b1ad5-110">Наиболее распространенными типами данных, которые являются срезами, являются списки и массивы F #.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="b1ad5-111">В следующем примере показано, как это сделать с помощью списков.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="b1ad5-112">Массивы срезов так же, как и списки срезов:</span><span class="sxs-lookup"><span data-stu-id="b1ad5-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="b1ad5-113">Многомерные массивы с срезами</span><span class="sxs-lookup"><span data-stu-id="b1ad5-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="b1ad5-114">F # поддерживает многомерные массивы в основной библиотеке F #.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="b1ad5-115">Как и в случае с одномерным массивами, можно также использовать срезы многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="b1ad5-116">Однако введение дополнительных измерений требует немного другого синтаксиса, чтобы можно было создавать срезы конкретных строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="b1ad5-117">В следующих примерах показано, как выполнить срез 2D-массива:</span><span class="sxs-lookup"><span data-stu-id="b1ad5-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

<span data-ttu-id="b1ad5-118">Основная библиотека F # в настоящее время не определена `GetSlice` для трехмерных массивов.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="b1ad5-119">Если вы хотите разделить трехмерные массивы или другие массивы большего размера, определите `GetSlice` элемент самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="b1ad5-120">Определение срезов для других структур данных</span><span class="sxs-lookup"><span data-stu-id="b1ad5-120">Defining slices for other data structures</span></span>

<span data-ttu-id="b1ad5-121">Основная библиотека F # определяет срезы для ограниченного набора типов.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="b1ad5-122">Если вы хотите определить срезы для большего числа типов данных, это можно сделать либо в самом определении типа, либо в расширении типа.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="b1ad5-123">Например, ниже показано, как можно определить срезы для класса, <xref:System.ArraySegment%601> чтобы обеспечить удобную обработку данных:</span><span class="sxs-lookup"><span data-stu-id="b1ad5-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

<span data-ttu-id="b1ad5-124">Еще один пример использования <xref:System.Span%601> <xref:System.ReadOnlySpan%601> типов и:</span><span class="sxs-lookup"><span data-stu-id="b1ad5-124">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="b1ad5-125">Встроенные срезы F # являются конечными включительно</span><span class="sxs-lookup"><span data-stu-id="b1ad5-125">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="b1ad5-126">Все внутренние срезы в F # являются конечными включительно. то есть верхняя граница включается в срез.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-126">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="b1ad5-127">Для данного среза с начальным индексом `x` и конечным индексом `y` результирующий срез будет включать значение *ИС* .</span><span class="sxs-lookup"><span data-stu-id="b1ad5-127">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="b1ad5-128">Встроенные пустые срезы F #</span><span class="sxs-lookup"><span data-stu-id="b1ad5-128">Built-in F# empty slices</span></span>

<span data-ttu-id="b1ad5-129">Списки F #, массивы, последовательности, строки, двумерные массивы, трехмерные массивы и массивы 4D будут создавать пустой срез, если синтаксис может привести к несуществующему срезу.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-129">F# lists, arrays, sequences, strings, 2D arrays, 3D arrays, and 4D arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="b1ad5-130">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-130">Consider the following:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

<span data-ttu-id="b1ad5-131">Разработчики на C# могут вызывать исключение, а не создавать пустой срез.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-131">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="b1ad5-132">Это решение проекта основано на том, что пустые коллекции состоят в F #.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-132">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="b1ad5-133">Пустой список F # можно составить с помощью другого списка F #, в существующую строку можно добавить пустую строку и т. д.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-133">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="b1ad5-134">Можно обычно создавать срезы на основе значений, переданных в качестве параметров, и предоставлять неограниченные границы, создавая пустую коллекцию путем создания пустой коллекции в соответствии с особенностями кода F #.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-134">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="b1ad5-135">Срезы с фиксированным индексом для массивов трехмерных и 4D</span><span class="sxs-lookup"><span data-stu-id="b1ad5-135">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="b1ad5-136">Для массивов 3D и 4D можно «исправить» определенный индекс и срез других измерений с фиксированным индексом.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-136">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="b1ad5-137">Чтобы проиллюстрировать это, рассмотрим следующий трехмерный массив:</span><span class="sxs-lookup"><span data-stu-id="b1ad5-137">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="b1ad5-138">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="b1ad5-138">*z = 0*</span></span>
| <span data-ttu-id="b1ad5-139">кс\и</span><span class="sxs-lookup"><span data-stu-id="b1ad5-139">x\y</span></span>   | <span data-ttu-id="b1ad5-140">0</span><span class="sxs-lookup"><span data-stu-id="b1ad5-140">0</span></span> | <span data-ttu-id="b1ad5-141">1</span><span class="sxs-lookup"><span data-stu-id="b1ad5-141">1</span></span> |
|-------|---|---|
| <span data-ttu-id="b1ad5-142">**0**</span><span class="sxs-lookup"><span data-stu-id="b1ad5-142">**0**</span></span> | <span data-ttu-id="b1ad5-143">0</span><span class="sxs-lookup"><span data-stu-id="b1ad5-143">0</span></span> | <span data-ttu-id="b1ad5-144">1</span><span class="sxs-lookup"><span data-stu-id="b1ad5-144">1</span></span> |
| <span data-ttu-id="b1ad5-145">**1**</span><span class="sxs-lookup"><span data-stu-id="b1ad5-145">**1**</span></span> | <span data-ttu-id="b1ad5-146">2</span><span class="sxs-lookup"><span data-stu-id="b1ad5-146">2</span></span> | <span data-ttu-id="b1ad5-147">3</span><span class="sxs-lookup"><span data-stu-id="b1ad5-147">3</span></span> |

<span data-ttu-id="b1ad5-148">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="b1ad5-148">*z = 1*</span></span>
| <span data-ttu-id="b1ad5-149">кс\и</span><span class="sxs-lookup"><span data-stu-id="b1ad5-149">x\y</span></span>   | <span data-ttu-id="b1ad5-150">0</span><span class="sxs-lookup"><span data-stu-id="b1ad5-150">0</span></span> | <span data-ttu-id="b1ad5-151">1</span><span class="sxs-lookup"><span data-stu-id="b1ad5-151">1</span></span> |
|-------|---|---|
| <span data-ttu-id="b1ad5-152">**0**</span><span class="sxs-lookup"><span data-stu-id="b1ad5-152">**0**</span></span> | <span data-ttu-id="b1ad5-153">4</span><span class="sxs-lookup"><span data-stu-id="b1ad5-153">4</span></span> | <span data-ttu-id="b1ad5-154">5</span><span class="sxs-lookup"><span data-stu-id="b1ad5-154">5</span></span> |
| <span data-ttu-id="b1ad5-155">**1**</span><span class="sxs-lookup"><span data-stu-id="b1ad5-155">**1**</span></span> | <span data-ttu-id="b1ad5-156">6</span><span class="sxs-lookup"><span data-stu-id="b1ad5-156">6</span></span> | <span data-ttu-id="b1ad5-157">7</span><span class="sxs-lookup"><span data-stu-id="b1ad5-157">7</span></span> |

<span data-ttu-id="b1ad5-158">Если необходимо извлечь срез `[| 4; 5 |]` из массива, используйте срез фиксированного индекса.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-158">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

```fsharp
let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="b1ad5-159">Последняя строка исправляет `y` и `z` индиЦиес трехмерного массива и принимает остальные `x` значения, соответствующие матрице.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-159">The last line fixes the `y` and `z` indicies of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1ad5-160">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b1ad5-160">See also</span></span>

- [<span data-ttu-id="b1ad5-161">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="b1ad5-161">Indexed properties</span></span>](./members/indexed-properties.md)
