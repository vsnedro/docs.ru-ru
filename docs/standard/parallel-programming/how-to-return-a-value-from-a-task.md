---
title: Практическое руководство. Возвращение значения из задачи
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 144d004d697b84a011cedafc7d07b679ef8852c3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288151"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="dcf2f-102">Практическое руководство. Возвращение значения из задачи</span><span class="sxs-lookup"><span data-stu-id="dcf2f-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="dcf2f-103">В этом примере показано, как использовать тип <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> для возврата значения из свойства <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="dcf2f-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="dcf2f-104">Здесь требуется, чтобы каталог C:\Users\Public\Pictures\Sample Pictures\ существовал и содержал файлы.</span><span class="sxs-lookup"><span data-stu-id="dcf2f-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcf2f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="dcf2f-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="dcf2f-106">Свойство <xref:System.Threading.Tasks.Task%601.Result%2A> блокирует вызывающий поток до завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="dcf2f-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="dcf2f-107">Дополнительные сведения о том, как передать результат одной <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> в задачу продолжения, см. в руководстве по [созданию цепочки задач с помощью задач продолжения](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="dcf2f-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf2f-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dcf2f-108">See also</span></span>

- [<span data-ttu-id="dcf2f-109">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="dcf2f-109">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="dcf2f-110">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="dcf2f-110">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
