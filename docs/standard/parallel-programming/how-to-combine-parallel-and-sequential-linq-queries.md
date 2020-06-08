---
title: Практическое руководство. Объединение параллельных и последовательных запросов LINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 2bdf074bc2977dc501e0726a52e825c89828565f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289542"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="d0ad8-102">Практическое руководство. Объединение параллельных и последовательных запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="d0ad8-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>

<span data-ttu-id="d0ad8-103">Этот пример демонстрирует применение метода <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, который запрашивает последовательную обработку в PLINQ всех последующих операторов текущего запроса.</span><span class="sxs-lookup"><span data-stu-id="d0ad8-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="d0ad8-104">Обычно последовательная обработка выполняется медленнее, чем параллельная, но иногда она необходима, чтобы гарантировать правильные результаты.</span><span class="sxs-lookup"><span data-stu-id="d0ad8-104">Although sequential processing is often slower than parallel, sometimes it's necessary to produce correct results.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0ad8-105">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="d0ad8-105">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="d0ad8-106">См. дополнительные сведения об [ускорении выполнения в PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="d0ad8-106">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0ad8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d0ad8-107">Example</span></span>  
 <span data-ttu-id="d0ad8-108">Следующий пример демонстрирует одну из ситуаций, для которой необходимо <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, поскольку здесь важно сохранить порядок, установленный предыдущим предложением запроса.</span><span class="sxs-lookup"><span data-stu-id="d0ad8-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0ad8-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d0ad8-109">Compiling the Code</span></span>  
 <span data-ttu-id="d0ad8-110">Чтобы скомпилировать и запустить этот код, вставьте его в проект [Пример данных PLINQ](plinq-data-sample.md), добавьте строку с вызовом этого метода из `Main` и нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="d0ad8-110">To compile and run this code, paste it into the [PLINQ Data Sample](plinq-data-sample.md) project, add a line to call the method from `Main`, and press **F5**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ad8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d0ad8-111">See also</span></span>

- [<span data-ttu-id="d0ad8-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d0ad8-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
