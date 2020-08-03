---
title: Руководство по программированию на C#. Массивы как объекты
description: В C# массивы представляют собой объекты массива абстрактного базового типа. Можно использовать свойства и другие члены класса массива, например свойство Length.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474726"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="06fea-104">Массивы как объекты (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="06fea-104">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="06fea-105">В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++.</span><span class="sxs-lookup"><span data-stu-id="06fea-105">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="06fea-106"><xref:System.Array> — это абстрактный базовый тип для всех типов массивов.</span><span class="sxs-lookup"><span data-stu-id="06fea-106"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="06fea-107">Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="06fea-107">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="06fea-108">Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива.</span><span class="sxs-lookup"><span data-stu-id="06fea-108">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="06fea-109">В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="06fea-109">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="06fea-110">В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.</span><span class="sxs-lookup"><span data-stu-id="06fea-110">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="06fea-111">Пример</span><span class="sxs-lookup"><span data-stu-id="06fea-111">Example</span></span>

<span data-ttu-id="06fea-112">В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="06fea-112">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="06fea-113">См. также</span><span class="sxs-lookup"><span data-stu-id="06fea-113">See also</span></span>

- [<span data-ttu-id="06fea-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="06fea-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="06fea-115">Массивы</span><span class="sxs-lookup"><span data-stu-id="06fea-115">Arrays</span></span>](./index.md)
- [<span data-ttu-id="06fea-116">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="06fea-116">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="06fea-117">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="06fea-117">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="06fea-118">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="06fea-118">Jagged Arrays</span></span>](./jagged-arrays.md)
