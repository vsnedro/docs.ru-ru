---
title: Практическое руководство. Реализация формы, в которой выполняется фоновая операция
description: Узнайте, как реализовать форму Windows, которая использует фоновую операцию, чтобы одна операция продолжала работать, пока продолжается другая операция.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 23bf4bc02fbf998d92dfce6d84e4e337cbefe7d9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174527"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="428ab-103">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="428ab-103">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="428ab-104">В примере ниже программа создает форму, которая вычисляет числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="428ab-104">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="428ab-105">Вычисление выполняется в потоке, отдельном от потока пользовательского интерфейса, поэтому в ходе вычисления пользовательский интерфейс продолжает выполняться без задержек.</span><span class="sxs-lookup"><span data-stu-id="428ab-105">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="428ab-106">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="428ab-106">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="428ab-107">См. также [Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="428ab-107">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="428ab-108">Пример</span><span class="sxs-lookup"><span data-stu-id="428ab-108">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="428ab-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="428ab-109">Compiling the Code</span></span>  
 <span data-ttu-id="428ab-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="428ab-110">This example requires:</span></span>  
  
- <span data-ttu-id="428ab-111">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="428ab-111">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="428ab-112">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="428ab-112">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="428ab-113">При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="428ab-113">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="428ab-114">Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../standard/threading/managed-threading-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="428ab-114">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428ab-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="428ab-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="428ab-116">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="428ab-116">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="428ab-117">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="428ab-117">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
