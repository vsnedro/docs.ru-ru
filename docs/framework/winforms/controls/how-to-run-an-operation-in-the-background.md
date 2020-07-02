---
title: Практическое руководство. Фоновое выполнение операции
description: Узнайте, как использовать класс BackgroundWorker для выполнения длительной операции Windows Forms в фоновом режиме.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 6b2a97f5acf1e906dfe141aee62e99a4e50dca9f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621578"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="e2e8a-103">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="e2e8a-103">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="e2e8a-104">Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-104">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="e2e8a-105">В примере ниже показано, как запустить операцию, занимающую длительное время, в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-105">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="e2e8a-106">В форме есть кнопки **Пуск** и **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-106">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="e2e8a-107">Кнопка **Пуск** служит для запуска асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-107">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="e2e8a-108">Кнопка **Отмена** служит для остановки асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-108">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="e2e8a-109">Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-109">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="e2e8a-110">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-110">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="e2e8a-111">См. также раздел [Пошаговое руководство. Фоновое выполнение операции](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="e2e8a-111">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2e8a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e2e8a-112">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e2e8a-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e2e8a-113">Compiling the Code</span></span>  
 <span data-ttu-id="e2e8a-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e2e8a-114">This example requires:</span></span>  
  
- <span data-ttu-id="e2e8a-115">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e2e8a-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e8a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e2e8a-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="e2e8a-117">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="e2e8a-117">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="e2e8a-118">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="e2e8a-118">BackgroundWorker Component</span></span>](backgroundworker-component.md)
