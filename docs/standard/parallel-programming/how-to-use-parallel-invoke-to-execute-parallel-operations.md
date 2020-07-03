---
title: Практическое руководство. Использование Parallel.Invoke для выполнения параллельных операций
description: Узнайте, как использовать метод Parallel.Invoke из библиотеки параллельных задач (TPL), который выполняет параллельные операции с общим источником данных в .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 084ade48b1406d23a11eb311739525f35ac973df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596349"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="93a50-103">Практическое руководство. Использование Parallel.Invoke для выполнения параллельных операций</span><span class="sxs-lookup"><span data-stu-id="93a50-103">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="93a50-104">В этом примере показывается, как параллелизовать операции с помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> в библиотеке параллельных задач.</span><span class="sxs-lookup"><span data-stu-id="93a50-104">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="93a50-105">В общем источнике данных выполняются три операции.</span><span class="sxs-lookup"><span data-stu-id="93a50-105">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="93a50-106">Они могут выполняться параллельно простым способом, поскольку ни одна из этих операций не изменяет источник.</span><span class="sxs-lookup"><span data-stu-id="93a50-106">The operations can be executed in parallel in a straightforward manner, because none of them modifies the source.</span></span>

> [!NOTE]
> <span data-ttu-id="93a50-107">В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="93a50-107">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="93a50-108">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. статью [Лямбда-выражения в PLINQ и библиотеке параллельных задач](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="93a50-108">If you aren't familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="93a50-109">Пример</span><span class="sxs-lookup"><span data-stu-id="93a50-109">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="93a50-110">С помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> можно просто указать, какие действия должны выполняться параллельно, и среда выполнения обработает все сведения по планированию потока, включая автоматическое масштабирование на число ядер в главном компьютере.</span><span class="sxs-lookup"><span data-stu-id="93a50-110">With <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="93a50-111">В этом примере параллелизуются операции, но не данные.</span><span class="sxs-lookup"><span data-stu-id="93a50-111">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="93a50-112">Как вариант можно параллелизовать запросы LINQ с помощью PLINQ и выполнять эти запросы последовательно.</span><span class="sxs-lookup"><span data-stu-id="93a50-112">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="93a50-113">Кроме того, можно параллелизовать данные с помощью PLINQ.</span><span class="sxs-lookup"><span data-stu-id="93a50-113">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="93a50-114">Другим вариантом является параллелизация запросов и задач.</span><span class="sxs-lookup"><span data-stu-id="93a50-114">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="93a50-115">Хотя итоговая нагрузка может снизить производительность главных компьютеров с относительно небольшим числом процессоров, масштабирование выполняется лучше на компьютерах с большим числом процессоров.</span><span class="sxs-lookup"><span data-stu-id="93a50-115">Although the resulting overhead might degrade performance on host computers with relatively few processors, it scales better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="93a50-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="93a50-116">Compile the Code</span></span>

<span data-ttu-id="93a50-117">Скопируйте и вставьте весь пример в проект Microsoft Visual Studio и нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="93a50-117">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="93a50-118">См. также</span><span class="sxs-lookup"><span data-stu-id="93a50-118">See also</span></span>

- [<span data-ttu-id="93a50-119">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="93a50-119">Parallel Programming</span></span>](index.md)
- [<span data-ttu-id="93a50-120">Практическое руководство. Отмена задачи и ее дочерних элементов</span><span class="sxs-lookup"><span data-stu-id="93a50-120">How to: Cancel a Task and Its Children</span></span>](how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="93a50-121">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="93a50-121">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
