---
title: Секционирование данных (C#)
description: Сведения о секционировании данных в LINQ. Просмотрите пример, в котором показаны результаты операций секционирования.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 31beacd672addb3eb38ade8f2bf9cfae25f4d27a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176270"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="4a755-104">Секционирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="4a755-104">Partitioning Data (C#)</span></span>

<span data-ttu-id="4a755-105">Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.</span><span class="sxs-lookup"><span data-stu-id="4a755-105">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="4a755-106">На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="4a755-106">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="4a755-107">Первая операция возвращает первые три элемента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="4a755-107">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="4a755-108">Вторая операция пропускает первые три элемента и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="4a755-108">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="4a755-109">Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.</span><span class="sxs-lookup"><span data-stu-id="4a755-109">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Рисунок иллюстрирующий три операции секционирования LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="4a755-111">Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.</span><span class="sxs-lookup"><span data-stu-id="4a755-111">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="4a755-112">Операторы</span><span class="sxs-lookup"><span data-stu-id="4a755-112">Operators</span></span>  
  
|<span data-ttu-id="4a755-113">Имя оператора</span><span class="sxs-lookup"><span data-stu-id="4a755-113">Operator Name</span></span>|<span data-ttu-id="4a755-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4a755-114">Description</span></span>|<span data-ttu-id="4a755-115">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="4a755-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="4a755-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4a755-116">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="4a755-117">Skip</span><span class="sxs-lookup"><span data-stu-id="4a755-117">Skip</span></span>|<span data-ttu-id="4a755-118">Пропускает элементы до указанной позиции в последовательности.</span><span class="sxs-lookup"><span data-stu-id="4a755-118">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="4a755-119">Не применяется</span><span class="sxs-lookup"><span data-stu-id="4a755-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4a755-120">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4a755-120">SkipWhile</span></span>|<span data-ttu-id="4a755-121">Пропускает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="4a755-121">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="4a755-122">Не применяется</span><span class="sxs-lookup"><span data-stu-id="4a755-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4a755-123">Take</span><span class="sxs-lookup"><span data-stu-id="4a755-123">Take</span></span>|<span data-ttu-id="4a755-124">Возвращает элементы на указанную позицию в последовательности.</span><span class="sxs-lookup"><span data-stu-id="4a755-124">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="4a755-125">Не применяется</span><span class="sxs-lookup"><span data-stu-id="4a755-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4a755-126">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4a755-126">TakeWhile</span></span>|<span data-ttu-id="4a755-127">Принимает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="4a755-127">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="4a755-128">Не применяется</span><span class="sxs-lookup"><span data-stu-id="4a755-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="4a755-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4a755-129">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="4a755-130">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="4a755-130">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
