---
title: Отмена асинхронных задач после определенного периода времени (C#)
description: Узнайте, как запланировать отмену всех связанных задач, которые не были завершены в течение определенного периода времени.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: ad9064f8f45a737982ffc35ab4ea2395ddae9016
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811422"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="756ee-103">Отмена асинхронных задач после определенного периода времени (C#)</span><span class="sxs-lookup"><span data-stu-id="756ee-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="756ee-104">Если не нужно дожидаться, пока завершится выполнение асинхронной операции, ее можно отменить по истечении определенного периода времени с помощью метода <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="756ee-104">You can cancel an asynchronous operation after a period of time by using the <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="756ee-105">Этот метод планирует отмену всех связанных задач, не завершенных в течение времени, установленного выражением `CancelAfter`.</span><span class="sxs-lookup"><span data-stu-id="756ee-105">This method schedules the cancellation of any associated tasks that aren't complete within the period of time that's designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="756ee-106">В этом примере добавляется код, составленный в разделе [Отмена списка задач (C#)](cancel-an-async-task-or-a-list-of-tasks.md), для загрузки списка веб-сайтов и отображения длины содержимого каждого из них.</span><span class="sxs-lookup"><span data-stu-id="756ee-106">This example adds to the code that's developed in [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

<span data-ttu-id="756ee-107">Темы, рассматриваемые в этом руководстве:</span><span class="sxs-lookup"><span data-stu-id="756ee-107">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="756ee-108">Обновление существующего консольного приложения .NET</span><span class="sxs-lookup"><span data-stu-id="756ee-108">Updating an existing .NET console application</span></span>
> - <span data-ttu-id="756ee-109">Планирование отмены</span><span class="sxs-lookup"><span data-stu-id="756ee-109">Scheduling a cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="756ee-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="756ee-110">Prerequisites</span></span>

<span data-ttu-id="756ee-111">Для работы с данным учебником требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="756ee-111">This tutorial requires the following:</span></span>

- <span data-ttu-id="756ee-112">Предполагается, что вы создали приложение в учебнике [Отмена списка задач (C#)](cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="756ee-112">You're expected to have created an application in the [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) tutorial</span></span>
- [<span data-ttu-id="756ee-113">Пакет SDK для .NET 5.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="756ee-113">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="756ee-114">Интегрированная среда разработки (IDE)</span><span class="sxs-lookup"><span data-stu-id="756ee-114">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="756ee-115">Мы рекомендуем Visual Studio, Visual Studio Code или Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="756ee-115">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a><span data-ttu-id="756ee-116">Обновление точки входа приложения</span><span class="sxs-lookup"><span data-stu-id="756ee-116">Update application entry point</span></span>

<span data-ttu-id="756ee-117">Замените существующий метод `Main` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="756ee-117">Replace the existing `Main` method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="756ee-118">Обновленный метод `Main` записывает в консоль несколько инструкций.</span><span class="sxs-lookup"><span data-stu-id="756ee-118">The updated `Main` method writes a few instructional messages to the console.</span></span> <span data-ttu-id="756ee-119">[Попробуйте перехватить](../../../language-reference/keywords/try-catch.md), вызвав <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType>, чтобы запланировать отмену.</span><span class="sxs-lookup"><span data-stu-id="756ee-119">Within the [try catch](../../../language-reference/keywords/try-catch.md), a call to <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> to schedule a cancellation.</span></span> <span data-ttu-id="756ee-120">Эта операция будет сообщать об отмене по истечении определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="756ee-120">This will signal cancellation after a period of time.</span></span>

<span data-ttu-id="756ee-121">Затем ожидается метод `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="756ee-121">Next, the `SumPageSizesAsync` method is awaited.</span></span> <span data-ttu-id="756ee-122">Если обработка всех URL-адресов выполняется быстрее запланированной отмены, приложение завершается.</span><span class="sxs-lookup"><span data-stu-id="756ee-122">If processing all of the URLs occurs faster than the scheduled cancellation, the application ends.</span></span> <span data-ttu-id="756ee-123">Однако если запланированная отмена запускается до обработки всех URL-адресов, создается <xref:System.Threading.Tasks.TaskCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="756ee-123">However, if the scheduled cancellation is triggered before all of the URLs are processed, a <xref:System.Threading.Tasks.TaskCanceledException> is thrown.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="756ee-124">Пример выходных данных приложения</span><span class="sxs-lookup"><span data-stu-id="756ee-124">Example application output</span></span>

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="756ee-125">Полный пример</span><span class="sxs-lookup"><span data-stu-id="756ee-125">Complete example</span></span>

<span data-ttu-id="756ee-126">Приведенный ниже код — это полный текст файла *Program.cs* для примера.</span><span class="sxs-lookup"><span data-stu-id="756ee-126">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="756ee-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="756ee-127">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="756ee-128">Асинхронное программирование с использованием ключевых слов Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="756ee-128">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="756ee-129">Отмена списка задач (C#)</span><span class="sxs-lookup"><span data-stu-id="756ee-129">Cancel a list of tasks (C#)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
