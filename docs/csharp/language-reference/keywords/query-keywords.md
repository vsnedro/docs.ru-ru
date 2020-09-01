---
description: Ключевые слова запроса. Справочник по C#
title: Ключевые слова запроса. Справочник по C#
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 0beea8634d13222aa18f14d79fdbd95a35cc832e
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137140"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="ace75-103">Ключевые слова запроса (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ace75-103">Query keywords (C# Reference)</span></span>

<span data-ttu-id="ace75-104">В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="ace75-104">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ace75-105">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="ace75-105">In this section</span></span>

|<span data-ttu-id="ace75-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="ace75-106">Clause</span></span>|<span data-ttu-id="ace75-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ace75-107">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="ace75-108">from</span><span class="sxs-lookup"><span data-stu-id="ace75-108">from</span></span>](from-clause.md)|<span data-ttu-id="ace75-109">Задает источник данных и переменную диапазона (аналогично переменной итерации).</span><span class="sxs-lookup"><span data-stu-id="ace75-109">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="ace75-110">where</span><span class="sxs-lookup"><span data-stu-id="ace75-110">where</span></span>](where-clause.md)|<span data-ttu-id="ace75-111">Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="ace75-111">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="ace75-112">select</span><span class="sxs-lookup"><span data-stu-id="ace75-112">select</span></span>](select-clause.md)|<span data-ttu-id="ace75-113">Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="ace75-113">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="ace75-114">group</span><span class="sxs-lookup"><span data-stu-id="ace75-114">group</span></span>](group-clause.md)|<span data-ttu-id="ace75-115">Группирует результаты запроса по заданному значению ключа.</span><span class="sxs-lookup"><span data-stu-id="ace75-115">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="ace75-116">into</span><span class="sxs-lookup"><span data-stu-id="ace75-116">into</span></span>](into.md)|<span data-ttu-id="ace75-117">Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.</span><span class="sxs-lookup"><span data-stu-id="ace75-117">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="ace75-118">orderby</span><span class="sxs-lookup"><span data-stu-id="ace75-118">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="ace75-119">Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="ace75-119">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="ace75-120">join</span><span class="sxs-lookup"><span data-stu-id="ace75-120">join</span></span>](join-clause.md)|<span data-ttu-id="ace75-121">Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.</span><span class="sxs-lookup"><span data-stu-id="ace75-121">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="ace75-122">let</span><span class="sxs-lookup"><span data-stu-id="ace75-122">let</span></span>](let-clause.md)|<span data-ttu-id="ace75-123">Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="ace75-123">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="ace75-124">in</span><span class="sxs-lookup"><span data-stu-id="ace75-124">in</span></span>](in.md)|<span data-ttu-id="ace75-125">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ace75-125">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="ace75-126">on</span><span class="sxs-lookup"><span data-stu-id="ace75-126">on</span></span>](on.md)|<span data-ttu-id="ace75-127">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ace75-127">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="ace75-128">equals</span><span class="sxs-lookup"><span data-stu-id="ace75-128">equals</span></span>](equals.md)|<span data-ttu-id="ace75-129">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ace75-129">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="ace75-130">by</span><span class="sxs-lookup"><span data-stu-id="ace75-130">by</span></span>](by.md)|<span data-ttu-id="ace75-131">Контекстное ключевое слово в предложении [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ace75-131">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="ace75-132">ascending</span><span class="sxs-lookup"><span data-stu-id="ace75-132">ascending</span></span>](ascending.md)|<span data-ttu-id="ace75-133">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ace75-133">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="ace75-134">descending</span><span class="sxs-lookup"><span data-stu-id="ace75-134">descending</span></span>](descending.md)|<span data-ttu-id="ace75-135">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ace75-135">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ace75-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ace75-136">See also</span></span>

- [<span data-ttu-id="ace75-137">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ace75-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ace75-138">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="ace75-138">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="ace75-139">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="ace75-139">LINQ in C#</span></span>](../../linq/index.md)
