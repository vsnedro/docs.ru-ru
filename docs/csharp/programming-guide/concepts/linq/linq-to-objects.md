---
title: LINQ to Objects (C#)
description: Узнайте о LINQ to Objects в C#, когда используются запросы LINQ с любой коллекцией IEnumerable или IEnumerable<T> без промежуточного поставщика LINQ или API LINQ.
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 575708f14487670a4371d470dcdcf650b03c3175
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202530"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="6256e-103">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-103">LINQ to Objects (C#)</span></span>

<span data-ttu-id="6256e-104">Термин "LINQ to Objects" означает использование запросов LINQ с любой коллекцией <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> напрямую, без привлечения промежуточного поставщика LINQ, API [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) или [LINQ to XML](../../../../standard/linq/linq-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6256e-104">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](../../../../standard/linq/linq-xml-overview.md).</span></span> <span data-ttu-id="6256e-105">Вы можете выполнить запрос LINQ к любой перечислимой коллекции, такой как <xref:System.Collections.Generic.List%601>, <xref:System.Array> или <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="6256e-105">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="6256e-106">Коллекция может быть определена пользователем или возвращена API .NET.</span><span class="sxs-lookup"><span data-stu-id="6256e-106">The collection may be user-defined or may be returned by a .NET API.</span></span>  
  
 <span data-ttu-id="6256e-107">В общем смысле LINQ to Objects представляет собой новый подход к коллекциям.</span><span class="sxs-lookup"><span data-stu-id="6256e-107">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="6256e-108">Раньше нужно было написать сложные циклы `foreach`, определяющие порядок извлечения данных из коллекции.</span><span class="sxs-lookup"><span data-stu-id="6256e-108">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="6256e-109">При использовании LINQ пишется декларативный код, описывающий, какие данные необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="6256e-109">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="6256e-110">Кроме того, запросы LINQ предлагают три основных преимущества по сравнению с традиционными циклами `foreach`:</span><span class="sxs-lookup"><span data-stu-id="6256e-110">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
- <span data-ttu-id="6256e-111">Они более краткие и удобочитаемые, особенно при фильтрации нескольких условий.</span><span class="sxs-lookup"><span data-stu-id="6256e-111">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
- <span data-ttu-id="6256e-112">Они предоставляют широкие возможности фильтрации, упорядочивания и группировки с минимумом кода приложения.</span><span class="sxs-lookup"><span data-stu-id="6256e-112">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
- <span data-ttu-id="6256e-113">Они могут переноситься в другие источники данных практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="6256e-113">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="6256e-114">В общем, чем сложнее операция, которую нужно выполнить с данными, тем больше преимуществ вы получаете при использовании LINQ вместо традиционных способов итерации.</span><span class="sxs-lookup"><span data-stu-id="6256e-114">In general, the more complex the operation you want to perform on the data, the more benefit you'll realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="6256e-115">Целью этого раздела является демонстрация подхода LINQ с помощью нескольких примеров.</span><span class="sxs-lookup"><span data-stu-id="6256e-115">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="6256e-116">Он не претендует на исчерпывающий характер.</span><span class="sxs-lookup"><span data-stu-id="6256e-116">It's not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6256e-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6256e-117">In This Section</span></span>  

 [<span data-ttu-id="6256e-118">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-118">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="6256e-119">Использование LINQ для запроса и преобразования строк и коллекций строк.</span><span class="sxs-lookup"><span data-stu-id="6256e-119">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="6256e-120">Ссылки на статьи, демонстрирующие эти принципы.</span><span class="sxs-lookup"><span data-stu-id="6256e-120">Also includes links to articles that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="6256e-121">LINQ и отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-121">LINQ and Reflection (C#)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 <span data-ttu-id="6256e-122">Ссылки на пример, демонстрирующий, как LINQ использует отражение.</span><span class="sxs-lookup"><span data-stu-id="6256e-122">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="6256e-123">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-123">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="6256e-124">Использование LINQ для взаимодействия с файловыми системами.</span><span class="sxs-lookup"><span data-stu-id="6256e-124">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="6256e-125">Ссылки на статьи, демонстрирующие эти понятия.</span><span class="sxs-lookup"><span data-stu-id="6256e-125">Also includes links to articles that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="6256e-126">Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-126">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="6256e-127">Выполнение запроса ArrayList в C#.</span><span class="sxs-lookup"><span data-stu-id="6256e-127">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="6256e-128">Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-128">How to add custom methods for LINQ queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="6256e-129">Расширение набора методов, которые можно использовать для запросов LINQ путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="6256e-129">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="6256e-130">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="6256e-130">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="6256e-131">Ссылки на статьи, рассказывающие LINQ и содержащие примеры кода выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="6256e-131">Provides links to articles that explain LINQ and provide examples of code that perform queries.</span></span>
