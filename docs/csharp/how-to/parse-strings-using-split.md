---
title: Анализ строк с помощью метода String.Split (руководство по языку C#)
description: Метод Split возвращает массив строк, разбитых по набору разделителей. Это простой и удобный способ анализа строк.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 7c5d8fa462775c6f3a9981693129997dda6c2286
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324137"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="4422d-104">Анализ строк с помощью метода String.Split в C\#</span><span class="sxs-lookup"><span data-stu-id="4422d-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="4422d-105">Метод <xref:System.String.Split%2A?displayProperty=nameWithType> создает массив подстрок, разбивая входную строку по одному или нескольким разделителям.</span><span class="sxs-lookup"><span data-stu-id="4422d-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="4422d-106">Этот метод зачастую является самым простым способом разделить строку по границам слов.</span><span class="sxs-lookup"><span data-stu-id="4422d-106">This method is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="4422d-107">Он также используется для разбиения строк по другим конкретным символам или строкам.</span><span class="sxs-lookup"><span data-stu-id="4422d-107">It's also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="4422d-108">Следующий код разбивает обычную фразу на массив строк для каждого слова.</span><span class="sxs-lookup"><span data-stu-id="4422d-108">The following code splits a common phrase into an array of strings for each word.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

<span data-ttu-id="4422d-109">Каждый экземпляр знака разделения создает значение в возвращаемом массиве.</span><span class="sxs-lookup"><span data-stu-id="4422d-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="4422d-110">Последовательные знаки разделения создают пустую строку в виде значения в возвращаемом массиве.</span><span class="sxs-lookup"><span data-stu-id="4422d-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="4422d-111">В следующем примере показано создание пустой строки с использованием символа пробела в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="4422d-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

<span data-ttu-id="4422d-112">Такое поведение упрощает работу с такими форматами, как файл данных с разделителями-запятыми (CSV), которые представляют табличные данные.</span><span class="sxs-lookup"><span data-stu-id="4422d-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="4422d-113">Идущие подряд запятые представляют пустой столбец.</span><span class="sxs-lookup"><span data-stu-id="4422d-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="4422d-114">Чтобы исключить из возвращаемого массива все пустые строки, можно передать необязательный параметр <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4422d-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="4422d-115">Для более сложной обработки возвращенной коллекции можно использовать [LINQ](../programming-guide/concepts/linq/index.md), чтобы управлять результирующей последовательностью.</span><span class="sxs-lookup"><span data-stu-id="4422d-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="4422d-116"><xref:System.String.Split%2A?displayProperty=nameWithType> может использовать несколько знаков разделения.</span><span class="sxs-lookup"><span data-stu-id="4422d-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="4422d-117">В приведенном ниже примере в качестве знаков разделения используются пробелы, запятые, точки, двоеточия и символы табуляции, которые передаются в <xref:System.String.Split%2A> в массиве.</span><span class="sxs-lookup"><span data-stu-id="4422d-117">The following example uses spaces, commas, periods, colons, and tabs as separating characters, which are passed to <xref:System.String.Split%2A> in an array .</span></span>
<span data-ttu-id="4422d-118">Цикл в конце кода отображает каждое из слов в возвращенном массиве.</span><span class="sxs-lookup"><span data-stu-id="4422d-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

<span data-ttu-id="4422d-119">Последовательные экземпляры любого разделителя создают пустую строку в выходном массиве:</span><span class="sxs-lookup"><span data-stu-id="4422d-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<span data-ttu-id="4422d-120">Метод <xref:System.String.Split%2A?displayProperty=nameWithType> может принимать массив строк (в этом случае в качестве разделителей при анализе целевой строки используются последовательности символов, а не отдельные символы).</span><span class="sxs-lookup"><span data-stu-id="4422d-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a><span data-ttu-id="4422d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4422d-121">See also</span></span>

- [<span data-ttu-id="4422d-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4422d-122">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="4422d-123">Строки</span><span class="sxs-lookup"><span data-stu-id="4422d-123">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="4422d-124">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="4422d-124">.NET regular expressions</span></span>](../../standard/base-types/regular-expressions.md)
