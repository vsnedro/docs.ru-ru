---
title: Руководство по программированию на C#. Одномерные массивы
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: e189253eedc21fa2d51e16407f04b034610bb57b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410248"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="bb505-102">Одномерные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="bb505-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="bb505-103">Для создания одномерного массива используется оператор [new](../../language-reference/operators/new-operator.md) и указывается тип элементов массива и число элементов.</span><span class="sxs-lookup"><span data-stu-id="bb505-103">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="bb505-104">В следующем примере показано объявление массива, содержащего пять целых чисел:</span><span class="sxs-lookup"><span data-stu-id="bb505-104">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="bb505-105">Этот массив содержит элементы с `array[0]` по `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="bb505-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="bb505-106">Элементы массива элементы инициализируются до значения по умолчанию для типа элемента. Для целых чисел это `0`.</span><span class="sxs-lookup"><span data-stu-id="bb505-106">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="bb505-107">Массивы могут хранить любой указанный тип элемента. Например, в следующем примере приводится объявление массива строк:</span><span class="sxs-lookup"><span data-stu-id="bb505-107">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="bb505-108">Инициализация массива</span><span class="sxs-lookup"><span data-stu-id="bb505-108">Array Initialization</span></span>

<span data-ttu-id="bb505-109">Элементы массива можно инициализировать при объявлении.</span><span class="sxs-lookup"><span data-stu-id="bb505-109">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="bb505-110">В этом случае не требуется спецификатор длины, поскольку он уже задан по числу элементов в списке инициализации.</span><span class="sxs-lookup"><span data-stu-id="bb505-110">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="bb505-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb505-111">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="bb505-112">Ниже приведено объявление массива строк, где каждый элемент массива инициализируется с использованием названия дня:</span><span class="sxs-lookup"><span data-stu-id="bb505-112">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="bb505-113">Если массив инициализируется при объявлении, можно не использовать выражение `new` и тип массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bb505-113">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="bb505-114">Такой массив называется [неявно типизированным](implicitly-typed-arrays.md):</span><span class="sxs-lookup"><span data-stu-id="bb505-114">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="bb505-115">Переменную массива можно объявить без ее создания, но при присвоении нового массива этой переменной необходимо использовать оператор `new`.</span><span class="sxs-lookup"><span data-stu-id="bb505-115">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="bb505-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb505-116">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="bb505-117">Массивы типов значений и ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="bb505-117">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="bb505-118">Рассмотрим следующее объявление массива:</span><span class="sxs-lookup"><span data-stu-id="bb505-118">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="bb505-119">Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="bb505-119">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="bb505-120">Если это тип значения, оператор создает массив из 10 элементов, каждый из которых имеет тип `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="bb505-120">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="bb505-121">Если `SomeType` является ссылочным типом, этот оператор создает массив из 10 элементов, каждый из которых инициализируется с использованием ссылки NULL.</span><span class="sxs-lookup"><span data-stu-id="bb505-121">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="bb505-122">В обоих случаях элементы инициализируются до значения по умолчанию для типа элемента.</span><span class="sxs-lookup"><span data-stu-id="bb505-122">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="bb505-123">См. дополнительные сведения о [типах значений](../../language-reference/builtin-types/value-types.md) и [ссылочных типах](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="bb505-123">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb505-124">См. также</span><span class="sxs-lookup"><span data-stu-id="bb505-124">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="bb505-125">Массивы</span><span class="sxs-lookup"><span data-stu-id="bb505-125">Arrays</span></span>](./index.md)
- [<span data-ttu-id="bb505-126">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="bb505-126">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="bb505-127">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="bb505-127">Jagged Arrays</span></span>](./jagged-arrays.md)
