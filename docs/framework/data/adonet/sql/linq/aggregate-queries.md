---
title: Статистические запросы
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 2085808d631d1d9f97573c557e9e66e07113df52
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554225"
---
# <a name="aggregate-queries"></a><span data-ttu-id="65bae-102">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="65bae-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="65bae-103">поддерживает агрегатные операторы `Average`, `Count`, `Max`, `Min` и `Sum`.</span><span class="sxs-lookup"><span data-stu-id="65bae-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="65bae-104">Обратите внимание на следующие характеристики агрегатных операторов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65bae-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="65bae-105">Агрегатные запросы выполняются немедленно.</span><span class="sxs-lookup"><span data-stu-id="65bae-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="65bae-106">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65bae-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="65bae-107">Агрегатные запросы обычно возвращают число, а не коллекцию.</span><span class="sxs-lookup"><span data-stu-id="65bae-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="65bae-108">Дополнительные сведения см. в разделе [операции агрегирования](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="65bae-108">For more information, see [Aggregation Operations](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="65bae-109">В анонимном типе вызвать агрегаты нельзя.</span><span class="sxs-lookup"><span data-stu-id="65bae-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="65bae-110">В следующих разделах используются примеры из учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="65bae-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="65bae-111">Дополнительные сведения см. в статье [Загрузка образцов баз данных](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="65bae-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65bae-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="65bae-112">In This Section</span></span>  
 [<span data-ttu-id="65bae-113">Возврат среднего значения из числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="65bae-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="65bae-114">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="65bae-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="65bae-115">Подсчет количества элементов в последовательности</span><span class="sxs-lookup"><span data-stu-id="65bae-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="65bae-116">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="65bae-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="65bae-117">Нахождение максимального значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="65bae-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="65bae-118">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="65bae-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="65bae-119">Нахождение минимального значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="65bae-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="65bae-120">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="65bae-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="65bae-121">Вычисление суммы значений в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="65bae-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="65bae-122">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="65bae-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="65bae-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="65bae-123">Related Sections</span></span>  
 [<span data-ttu-id="65bae-124">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="65bae-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="65bae-125">Содержит ссылки на запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] в Visual Basic и C#.</span><span class="sxs-lookup"><span data-stu-id="65bae-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="65bae-126">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="65bae-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="65bae-127">Содержит ссылки на разделы, в которых объясняются основные понятия для разработки запросов LINQ в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65bae-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="65bae-128">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="65bae-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="65bae-129">Объясняет, как работают запросы в LINQ.</span><span class="sxs-lookup"><span data-stu-id="65bae-129">Explains how queries work in LINQ.</span></span>
