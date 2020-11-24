---
title: Практическое руководство. Возврат значения из задачи
description: Узнайте, как использовать тип System.Threading.Tasks.Task<TResult> для возврата значения из свойства Result в .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: c7a4a683545c9ef0448d9cdce769aae79215aecf
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825615"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="875f8-103">Практическое руководство. Возврат значения из задачи</span><span class="sxs-lookup"><span data-stu-id="875f8-103">How to: Return a Value from a Task</span></span>
<span data-ttu-id="875f8-104">В этом примере показано, как использовать тип <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> для возврата значения из свойства <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="875f8-104">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="875f8-105">Здесь требуется, чтобы каталог C:\Users\Public\Pictures\Sample Pictures\ существовал и содержал файлы.</span><span class="sxs-lookup"><span data-stu-id="875f8-105">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="875f8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="875f8-106">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="875f8-107">Свойство <xref:System.Threading.Tasks.Task%601.Result%2A> блокирует вызывающий поток до завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="875f8-107">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="875f8-108">Дополнительные сведения о том, как передать результат одной <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> в задачу продолжения, см. в руководстве по [созданию цепочки задач с помощью задач продолжения](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="875f8-108">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875f8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="875f8-109">See also</span></span>

- [<span data-ttu-id="875f8-110">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="875f8-110">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="875f8-111">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="875f8-111">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
