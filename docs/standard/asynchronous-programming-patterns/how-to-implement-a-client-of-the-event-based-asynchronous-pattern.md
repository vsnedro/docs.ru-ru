---
title: Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: f834ce4a0ec2208eee80ce8c3ffebfa6fdeeb5b1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289412"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="a6450-102">Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="a6450-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="a6450-103">В приведенном ниже примере кода показано, как использовать компонент, который соответствует принципам [асинхронной модели на основе событий](event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a6450-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="a6450-104">В форме для этого примера используется компонент `PrimeNumberCalculator`, который описывается в статье [Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях](component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="a6450-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="a6450-105">Запустив проект с этим примером, вы увидите форму расчета простых чисел с сеткой и двумя кнопками: **Start New Task** (Выполнить новую задачу) и **Cancel** (Отменить).</span><span class="sxs-lookup"><span data-stu-id="a6450-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="a6450-106">Вы можете нажать кнопку **Start New Task** (Выполнить новую задачу) несколько раз подряд, и при каждом нажатии запустится асинхронная операция вычисления, которая проверяет, является ли случайное проверяемое число простым.</span><span class="sxs-lookup"><span data-stu-id="a6450-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="a6450-107">Форма периодически обновляется, отображая ход выполнения и накопленные результаты.</span><span class="sxs-lookup"><span data-stu-id="a6450-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="a6450-108">Каждой операции присваивается уникальный идентификатор задачи.</span><span class="sxs-lookup"><span data-stu-id="a6450-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="a6450-109">Результат вычисления отображается в столбце **Result** (Результат). Если проверяемое число не является простым, оно дополняется отметкой **Composite** (Составное) и значением его первого делителя.</span><span class="sxs-lookup"><span data-stu-id="a6450-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="a6450-110">Кнопка **Cancel** (Отменить) позволяет отменить все операции, ожидающие выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6450-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="a6450-111">Вы можете выбрать несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="a6450-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6450-112">Большинство чисел не будут простыми.</span><span class="sxs-lookup"><span data-stu-id="a6450-112">Most numbers will not be prime.</span></span> <span data-ttu-id="a6450-113">Если после нескольких операций вам не удастся найти простое число, просто запустите еще несколько задач. Рано или поздно простые числа будут обнаружены.</span><span class="sxs-lookup"><span data-stu-id="a6450-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6450-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a6450-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="a6450-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6450-115">See also</span></span>

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
