---
description: Предложение orderby. Справочник по C#
title: Предложение orderby. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142353"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="4c990-103">Предложение orderby (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4c990-103">orderby clause (C# Reference)</span></span>

<span data-ttu-id="4c990-104">В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания.</span><span class="sxs-lookup"><span data-stu-id="4c990-104">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="4c990-105">Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей.</span><span class="sxs-lookup"><span data-stu-id="4c990-105">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="4c990-106">Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="4c990-106">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="4c990-107">По умолчанию задан порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="4c990-107">The default sort order is ascending.</span></span> <span data-ttu-id="4c990-108">Также можно указать настраиваемую функцию сравнения.</span><span class="sxs-lookup"><span data-stu-id="4c990-108">You can also specify a custom comparer.</span></span> <span data-ttu-id="4c990-109">Тем не менее сделать это можно только с использованием синтаксиса на основе метода.</span><span class="sxs-lookup"><span data-stu-id="4c990-109">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="4c990-110">Дополнительные сведения см. в разделе [Сортировка данных](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="4c990-110">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="4c990-111">Пример</span><span class="sxs-lookup"><span data-stu-id="4c990-111">Example</span></span>

<span data-ttu-id="4c990-112">В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="4c990-112">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="4c990-113">(Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)</span><span class="sxs-lookup"><span data-stu-id="4c990-113">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="4c990-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4c990-114">Example</span></span>

<span data-ttu-id="4c990-115">В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.</span><span class="sxs-lookup"><span data-stu-id="4c990-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="4c990-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c990-116">Remarks</span></span>

<span data-ttu-id="4c990-117">Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c990-117">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="4c990-118">Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c990-118">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c990-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4c990-119">See also</span></span>

- [<span data-ttu-id="4c990-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4c990-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4c990-121">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4c990-121">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="4c990-122">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="4c990-122">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="4c990-123">предложение group</span><span class="sxs-lookup"><span data-stu-id="4c990-123">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="4c990-124">LINQ</span><span class="sxs-lookup"><span data-stu-id="4c990-124">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
