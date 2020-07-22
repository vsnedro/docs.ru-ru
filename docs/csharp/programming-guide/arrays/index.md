---
title: Руководство по программированию на C#. Массивы
description: Храните несколько переменных одного типа в структуре данных массива на C#. Объявите массив, указав тип или указав объект для хранения любого типа.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e302ff2e4c2488c4899c4eb99a666d2d322119ce
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474739"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="dcc18-104">Массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="dcc18-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="dcc18-105">В структуре данных массива можно хранить несколько переменных одного типа.</span><span class="sxs-lookup"><span data-stu-id="dcc18-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="dcc18-106">Чтобы объявить массив, следует указать тип его элементов.</span><span class="sxs-lookup"><span data-stu-id="dcc18-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="dcc18-107">Если требуется, чтобы массив мог хранить элементы любого типа, можно указать `object` в качестве его типа.</span><span class="sxs-lookup"><span data-stu-id="dcc18-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="dcc18-108">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="dcc18-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="dcc18-109">Пример</span><span class="sxs-lookup"><span data-stu-id="dcc18-109">Example</span></span>

<span data-ttu-id="dcc18-110">В следующих примерах создаются одномерные массивы, многомерные массивы и массивы массивов:</span><span class="sxs-lookup"><span data-stu-id="dcc18-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="dcc18-111">Общие сведения о массивах</span><span class="sxs-lookup"><span data-stu-id="dcc18-111">Array overview</span></span>

<span data-ttu-id="dcc18-112">Массив имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="dcc18-112">An array has the following properties:</span></span>

- <span data-ttu-id="dcc18-113">Массив может быть [одномерным](single-dimensional-arrays.md), [многомерным](multidimensional-arrays.md) или [массивом массивов](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="dcc18-113">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="dcc18-114">Количество измерений и длина каждого из измерений задаются, когда создается экземпляр массива.</span><span class="sxs-lookup"><span data-stu-id="dcc18-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="dcc18-115">Эти значения нельзя изменить во время существования экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dcc18-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="dcc18-116">Используемые по умолчанию значения числовых элементов массива равны нулю, и элементам ссылки присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="dcc18-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="dcc18-117">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="dcc18-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="dcc18-118">Массивы индексируются от нуля: массив с `n` элементами индексируется от `0` до `n-1`.</span><span class="sxs-lookup"><span data-stu-id="dcc18-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="dcc18-119">Элементы массива могут иметь любой тип, в том числе тип массива.</span><span class="sxs-lookup"><span data-stu-id="dcc18-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="dcc18-120">Типы массивов — это [ссылочные типы](../../language-reference/keywords/reference-types.md), производные от абстрактного базового типа <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="dcc18-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="dcc18-121">Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, вы можете просматривать в цикле [foreach](../../language-reference/keywords/foreach-in.md) любые массивы C#.</span><span class="sxs-lookup"><span data-stu-id="dcc18-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="dcc18-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="dcc18-122">Related sections</span></span>

- [<span data-ttu-id="dcc18-123">Массивы как объекты</span><span class="sxs-lookup"><span data-stu-id="dcc18-123">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="dcc18-124">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="dcc18-124">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="dcc18-125">Передача массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="dcc18-125">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="dcc18-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="dcc18-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dcc18-127">См. также</span><span class="sxs-lookup"><span data-stu-id="dcc18-127">See also</span></span>

- [<span data-ttu-id="dcc18-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dcc18-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="dcc18-129">Коллекции</span><span class="sxs-lookup"><span data-stu-id="dcc18-129">Collections</span></span>](../concepts/collections.md)
