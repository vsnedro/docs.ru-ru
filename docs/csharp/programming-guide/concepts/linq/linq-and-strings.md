---
title: LINQ и строки (C#)
description: LINQ позволяет запрашивать и преобразовывать строки и коллекции строк. Запросы LINQ можно комбинировать с традиционными строковыми функциями и регулярными выражениями C#.
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: 0500d821335659fa29dd4809513f38dac0a8b193
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556724"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="4a3bc-104">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-104">LINQ and strings (C#)</span></span>

<span data-ttu-id="4a3bc-105">LINQ можно использовать для запроса и преобразования строк и коллекций строк.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-105">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="4a3bc-106">При этом лучше всего его потенциал раскрывается при работе с частично структурированными данными в текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-106">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="4a3bc-107">Запросы LINQ можно комбинировать с традиционными строковыми функциями и регулярными выражениями.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-107">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="4a3bc-108">Например, используя метод <xref:System.String.Split%2A?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>, можно создать массив строк, который затем можно запрашивать или изменять с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-108">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="4a3bc-109">Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> можно использовать в предложении `where` запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-109">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="4a3bc-110">Также LINQ можно использовать для запроса или изменения результатов <xref:System.Text.RegularExpressions.MatchCollection>, возвращаемых регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-110">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="4a3bc-111">Методы, описанные в этом разделе, позволяют преобразовать частично структурированные текстовые данные в XML.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-111">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="4a3bc-112">См. сведения в руководстве по [созданию кода XML из CSV-файлов](../../../../standard/linq/generate-xml-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="4a3bc-112">For more information, see [How to generate XML from CSV files](../../../../standard/linq/generate-xml-csv-files.md).</span></span>

<span data-ttu-id="4a3bc-113">Примеры в этом разделе делятся на две категории:</span><span class="sxs-lookup"><span data-stu-id="4a3bc-113">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="4a3bc-114">Запрос блока текста</span><span class="sxs-lookup"><span data-stu-id="4a3bc-114">Querying a block of text</span></span>

<span data-ttu-id="4a3bc-115">Вы можете запрашивать, анализировать и изменять блоки текста, разбивая их на запрашиваемый массив строк меньшего размера с помощью методов <xref:System.String.Split%2A?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-115">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4a3bc-116">Исходный текст можно разбить на слова, предложения, абзацы, страницы или другие фрагменты, а затем применить другие способы фрагментации, необходимые для вашего запроса.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-116">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="4a3bc-117">Практическое руководство. Подсчет вхождений слова в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-117">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="4a3bc-118">Показывает, как использовать LINQ для простых запросов текста.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-118">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="4a3bc-119">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-119">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="4a3bc-120">Показывает, как разбивать текстовые файлы на произвольные фрагменты и выполнять запросы к каждой части.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-120">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="4a3bc-121">Практическое руководство. Запрос символов в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-121">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="4a3bc-122">Показывает, что строка является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-122">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="4a3bc-123">Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-123">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="4a3bc-124">Показывает, как выполнять сопоставление комплексных шаблонов с отфильтрованными результатами запросов, используя регулярные выражения в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-124">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="4a3bc-125">Запрос частично структурированных данных в текстовом формате</span><span class="sxs-lookup"><span data-stu-id="4a3bc-125">Querying semi-structured data in text format</span></span>

<span data-ttu-id="4a3bc-126">Многие типы текстовых файлов состоят из серии строк, которые часто имеют одинаковый формат, например, из файлов с разделителями табуляцией или запятыми либо из строк фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-126">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="4a3bc-127">После того как текстовый файл будет считан в память, можно использовать LINQ для запроса и (или) изменения строк.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-127">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="4a3bc-128">Кроме того, запросы LINQ упрощают задачу объединения данных из различных источников.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-128">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="4a3bc-129">Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-129">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="4a3bc-130">Показывает, как найти все строки, которые есть в одном списке, но отсутствуют в другом.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-130">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="4a3bc-131">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-131">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="4a3bc-132">Показывает, как сортировать текстовые строки по какому-либо слову или полю.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-132">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="4a3bc-133">Практическое руководство. Изменение порядка полей файла с разделителями (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-133">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="4a3bc-134">Показывает, как изменить порядок полей в строке CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-134">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="4a3bc-135">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-135">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="4a3bc-136">Показывает различные способы объединения списков строк.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-136">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="4a3bc-137">Заполнение коллекций объектов из нескольких источников (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="4a3bc-138">Показывает, как создавать коллекции объектов, используя в качестве источников данных сразу несколько текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-138">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="4a3bc-139">Объединение содержимого из файлов разных форматов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-139">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="4a3bc-140">Показывает, как объединить строки из двух списков в одну строку, используя ключ сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-140">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="4a3bc-141">Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-141">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="4a3bc-142">Показывает, как создавать файлы, используя в качестве источника данных одиночный файл.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-142">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="4a3bc-143">Практическое руководство. Вычисление значений столбцов в текстовом CSV-файле (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-143">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="4a3bc-144">Показывает, как выполнять математические расчеты на основе текстовых данных в CSV-файлах.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-144">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a3bc-145">См. также</span><span class="sxs-lookup"><span data-stu-id="4a3bc-145">See also</span></span>

- [<span data-ttu-id="4a3bc-146">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-146">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="4a3bc-147">Создание кода XML из CSV-файлов</span><span class="sxs-lookup"><span data-stu-id="4a3bc-147">How to generate XML from CSV files</span></span>](../../../../standard/linq/generate-xml-csv-files.md)
