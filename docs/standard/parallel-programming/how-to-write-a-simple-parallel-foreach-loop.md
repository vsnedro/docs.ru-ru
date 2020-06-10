---
title: Создание простой параллельной программы с использованием Parallel.ForEach
description: В этой статье описывается, как включить параллелизм данных в .NET. Напишите цикл Parallel.ForEach для любого источника данных IEnumerable или IEnumerable<T>.
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 59c8710a8e3fc878b2ceded8595f7f3319d4c953
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447203"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="8aa6f-104">Практическое руководство. написание простого цикла Parallel.ForEach</span><span class="sxs-lookup"><span data-stu-id="8aa6f-104">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="8aa6f-105">В этом примере показано, как использовать цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для включения параллелизма данных в любом источнике данных <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-105">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa6f-106">В этой документации для определения делегатов в PLINQ используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-106">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="8aa6f-107">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="8aa6f-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="8aa6f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8aa6f-108">Example</span></span>

<span data-ttu-id="8aa6f-109">В этом примере предполагается, что у вас есть несколько JPG-файлов в папке *C:\Пользователи\Общие\Изображения\Образцы изображений* и что будет создана новая вложенная папка *Измененные*.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-109">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="8aa6f-110">При выполнении примера каждое изображение JPG в папке *Образцы изображений* будет повернуто и сохранено в папку *Измененные*.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-110">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="8aa6f-111">Эти два пути при необходимости можно изменить.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-111">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="8aa6f-112">Цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> действует как цикл <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-112">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="8aa6f-113">Цикл разделяет исходную коллекцию на секции и распределяет задачи по нескольким потокам с учетом доступной среды системы.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-113">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="8aa6f-114">Чем больше в системе процессоров, тем быстрее выполняются параллельные методы.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-114">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="8aa6f-115">Для некоторых исходных коллекций, в зависимости от размера источника и типа выполняемых работ, последовательный цикл может оказаться быстрее.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-115">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="8aa6f-116">Дополнительные сведения о производительности см. в статье [Потенциальные ошибки, связанные с параллелизмом данных и задач](potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="8aa6f-116">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="8aa6f-117">Дополнительные сведения о параллельных циклах см. в статье [Практическое руководство. Написание простого цикла Parallel.For](how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="8aa6f-117">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="8aa6f-118">Чтобы применить <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для неуниверсальной коллекции, вы можете преобразовать ее в универсальную коллекцию с помощью метода расширения <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-118">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="8aa6f-119">Также вы можете использовать Parallel LINQ (PLINQ) для параллельной обработки источников данных <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-119">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="8aa6f-120">PLINQ позволяет применять декларативный синтаксис запроса для описания поведения цикла.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-120">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="8aa6f-121">Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](introduction-to-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="8aa6f-121">For more information, see [Parallel LINQ (PLINQ)](introduction-to-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="8aa6f-122">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-122">Compile and run the code</span></span>

<span data-ttu-id="8aa6f-123">Код можно скомпилировать как консольное приложение для .NET Framework или .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-123">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="8aa6f-124">В Visual Studio существуют шаблоны консольных приложений Visual Basic и C# для Windows Desktop и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-124">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="8aa6f-125">В командной строке можно использовать команды .NET Core CLI (например, `dotnet new console` или `dotnet new console -lang vb`). Также вы можете создать файл и использовать компилятор командной строки для приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-125">From the command line, you can use either the .NET Core CLI commands (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="8aa6f-126">Для проекта .NET Core необходимо сослаться на пакет NuGet **System.Drawing.Common**.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-126">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="8aa6f-127">В Visual Studio используйте диспетчер пакетов NuGet для установки пакета.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-127">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="8aa6f-128">Кроме того, вы можете добавить ссылку на пакет в файл \*.csproj или \*.vbproj:</span><span class="sxs-lookup"><span data-stu-id="8aa6f-128">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="8aa6f-129">Чтобы запустить консольное приложение .NET Core из командной строки, используйте `dotnet run` в папке, которая содержит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-129">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="8aa6f-130">Чтобы запустить консольное приложение из Visual Studio, нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="8aa6f-130">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8aa6f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8aa6f-131">See also</span></span>

- [<span data-ttu-id="8aa6f-132">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="8aa6f-132">Data parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="8aa6f-133">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="8aa6f-133">Parallel programming</span></span>](index.md)
- [<span data-ttu-id="8aa6f-134">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="8aa6f-134">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
