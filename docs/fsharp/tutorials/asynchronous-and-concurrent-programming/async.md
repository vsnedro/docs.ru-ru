---
title: Программирование Async
description: Узнайте, как Фз обеспечивает чистую поддержку асинхронности на основе модели программирования на языковом уровне, основанной на основных функциональных концепциях программирования.
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608040"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="23a4b-103">Программирование Async в F\#</span><span class="sxs-lookup"><span data-stu-id="23a4b-103">Async programming in F\#</span></span>

<span data-ttu-id="23a4b-104">Асинхронное программирование является механизмом, который имеет важное значение для современных приложений по разным причинам.</span><span class="sxs-lookup"><span data-stu-id="23a4b-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="23a4b-105">Существует два основных случая использования, с которыми столкнутся большинство разработчиков:</span><span class="sxs-lookup"><span data-stu-id="23a4b-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="23a4b-106">Представление серверного процесса, который может обслуживать значительное количество одновременных входящих запросов, при минимизации ресурсов системы, занятых при обработке запросов, ждет входных данных от систем или служб, внешних для этого процесса</span><span class="sxs-lookup"><span data-stu-id="23a4b-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="23a4b-107">Поддержание адаптивного uI или основного потока при одновременном прогрессе фоновой работы</span><span class="sxs-lookup"><span data-stu-id="23a4b-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="23a4b-108">Хотя фоновая работа часто включает в себя использование нескольких потоков, важно рассматривать понятия асинхронности и многопоточности отдельно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="23a4b-109">На самом деле, они являются отдельными проблемами, и одно не подразумевает другое.</span><span class="sxs-lookup"><span data-stu-id="23a4b-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="23a4b-110">Ниже приводится в этой статье описываетэто это более подробно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-110">What follows in this article describes this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="23a4b-111">Асинхрония определена</span><span class="sxs-lookup"><span data-stu-id="23a4b-111">Asynchrony defined</span></span>

<span data-ttu-id="23a4b-112">Предыдущий пункт - что асинхронность не зависит от использования нескольких потоков - стоит объяснить немного дальше.</span><span class="sxs-lookup"><span data-stu-id="23a4b-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="23a4b-113">Есть три понятия, которые иногда связаны, но строго независимо друг от друга:</span><span class="sxs-lookup"><span data-stu-id="23a4b-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="23a4b-114">Параллель; при выполнении нескольких вычислений в перекрывающихся периодах времени.</span><span class="sxs-lookup"><span data-stu-id="23a4b-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="23a4b-115">Параллелизм; когда несколько вычислений или несколько частей одной вычислений работают в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="23a4b-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="23a4b-116">Асинхронность; когда один или несколько вычислений могут выполняться отдельно от основного потока программы.</span><span class="sxs-lookup"><span data-stu-id="23a4b-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="23a4b-117">Все три ортогональных концепций, но могут быть легко conflated, особенно когда они используются вместе.</span><span class="sxs-lookup"><span data-stu-id="23a4b-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="23a4b-118">Например, может потребоваться параллельно еранды несколько асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="23a4b-119">Это не означает, что параллелизм или асинхронность подразумевают друг друга.</span><span class="sxs-lookup"><span data-stu-id="23a4b-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="23a4b-120">Если вы считаете, этимология слова "асинхронный", Есть две части участие:</span><span class="sxs-lookup"><span data-stu-id="23a4b-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="23a4b-121">"а", что означает "не".</span><span class="sxs-lookup"><span data-stu-id="23a4b-121">"a", meaning "not".</span></span>
- <span data-ttu-id="23a4b-122">"синхронный", что означает "в то же время".</span><span class="sxs-lookup"><span data-stu-id="23a4b-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="23a4b-123">Когда вы поставите эти два термина вместе, вы увидите, что "асинхронный" означает "не в то же время".</span><span class="sxs-lookup"><span data-stu-id="23a4b-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="23a4b-124">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="23a4b-124">That's it!</span></span> <span data-ttu-id="23a4b-125">В этом определении нет никаких последствий параллелизма или параллелизма.</span><span class="sxs-lookup"><span data-stu-id="23a4b-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="23a4b-126">Это также верно на практике.</span><span class="sxs-lookup"><span data-stu-id="23a4b-126">This is also true in practice.</span></span>

<span data-ttu-id="23a4b-127">В практическом плане асинхронные вычисления в ФЗ планируется выполнять независимо от основного потока программы.</span><span class="sxs-lookup"><span data-stu-id="23a4b-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="23a4b-128">Это не означает параллелизм или параллелизм, а также не означает, что вычисление всегда происходит в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="23a4b-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="23a4b-129">На самом деле, асинхронные вычисления могут даже выполняться синхронно, в зависимости от характера вычислений и среды, в которой выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="23a4b-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="23a4b-130">Основной вынос вы должны иметь в том, что асинхронные вычисления не зависят от основного потока программы.</span><span class="sxs-lookup"><span data-stu-id="23a4b-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="23a4b-131">Хотя есть несколько гарантий о том, когда и как выполняется асинхронная вычисления, существуют некоторые подходы к их организации и планированию.</span><span class="sxs-lookup"><span data-stu-id="23a4b-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="23a4b-132">В остальной части этой статьи рассматриваются основные концепции для асинхронности F и как использовать типы, функции и выражения, встроенные в F.</span><span class="sxs-lookup"><span data-stu-id="23a4b-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="23a4b-133">Ключевые понятия</span><span class="sxs-lookup"><span data-stu-id="23a4b-133">Core concepts</span></span>

<span data-ttu-id="23a4b-134">В F, асинхронное программирование сосредоточено вокруг трех основных концепций:</span><span class="sxs-lookup"><span data-stu-id="23a4b-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="23a4b-135">Тип, `Async<'T>` представляющий собой композитные асинхронные вычисления.</span><span class="sxs-lookup"><span data-stu-id="23a4b-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="23a4b-136">Функции `Async` модуля, позволяющие планировать асинхронную работу, составляют асинхронные вычисления и преобразуют асинхронные результаты.</span><span class="sxs-lookup"><span data-stu-id="23a4b-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="23a4b-137">Вычислительное `async { }` [выражение,](../../language-reference/computation-expressions.md)которое обеспечивает удобный синтаксис для создания и управления асинхронными вычислениями.</span><span class="sxs-lookup"><span data-stu-id="23a4b-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="23a4b-138">Вы можете увидеть эти три понятия в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="23a4b-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="23a4b-139">В примере `printTotalFileBytes` функция типа `string -> Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="23a4b-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="23a4b-140">Вызов функции на самом деле не выполняет асинхронные вычисления.</span><span class="sxs-lookup"><span data-stu-id="23a4b-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="23a4b-141">Вместо этого, `Async<unit>` он возвращает, что выступает в качестве *спецификации* работы, которая должна выполнять сяврону.</span><span class="sxs-lookup"><span data-stu-id="23a4b-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="23a4b-142">Оно `Async.AwaitTask` вызывает в своем теле, которое преобразовывает результат <xref:System.IO.File.ReadAllBytesAsync%2A> к соотвествуя типу.</span><span class="sxs-lookup"><span data-stu-id="23a4b-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="23a4b-143">Другой важной линией `Async.RunSynchronously`является призыв к .</span><span class="sxs-lookup"><span data-stu-id="23a4b-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="23a4b-144">Это одна из стартовых функций модуля Async, которую необходимо вызвать, если вы хотите выполнить асинхронные вычисления.</span><span class="sxs-lookup"><span data-stu-id="23a4b-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="23a4b-145">Это принципиальное отличие от базового стиля `async` программирования с C'/Visual.</span><span class="sxs-lookup"><span data-stu-id="23a4b-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="23a4b-146">В F-, асинхронные вычисления можно рассматривать как **холодные задачи**.</span><span class="sxs-lookup"><span data-stu-id="23a4b-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="23a4b-147">Они должны быть явно начали на самом деле выполнять.</span><span class="sxs-lookup"><span data-stu-id="23a4b-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="23a4b-148">Это имеет некоторые преимущества, так как позволяет комбинировать и последовательности асинхронных работ гораздо легче, чем в C- или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="23a4b-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="23a4b-149">Объедините асинхронные вычисления</span><span class="sxs-lookup"><span data-stu-id="23a4b-149">Combine asynchronous computations</span></span>

<span data-ttu-id="23a4b-150">Вот пример, который опирается на предыдущий, комбинируя вычисления:</span><span class="sxs-lookup"><span data-stu-id="23a4b-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="23a4b-151">Как вы можете `main` видеть, функция имеет довольно много больше звонков.</span><span class="sxs-lookup"><span data-stu-id="23a4b-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="23a4b-152">Концептуально он делает следующее:</span><span class="sxs-lookup"><span data-stu-id="23a4b-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="23a4b-153">Преобразование аргументов командной строки в `Async<unit>` вычисления с помощью `Array.map`.</span><span class="sxs-lookup"><span data-stu-id="23a4b-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="23a4b-154">Создайте `Async<'T[]>` расписание и `printTotalFileBytes` запуск вычислений параллельно при запуске.</span><span class="sxs-lookup"><span data-stu-id="23a4b-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="23a4b-155">`Async<unit>` Создайте, который будет запускать параллельные вычисления и игнорировать его результат.</span><span class="sxs-lookup"><span data-stu-id="23a4b-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="23a4b-156">Явно запускать последние `Async.RunSynchronously` вычисления с и блокировать, пока он не будет завершен.</span><span class="sxs-lookup"><span data-stu-id="23a4b-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="23a4b-157">Когда эта программа `printTotalFileBytes` выполняется, выполняется параллельно для каждого аргумента командной строки.</span><span class="sxs-lookup"><span data-stu-id="23a4b-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="23a4b-158">Поскольку асинхронные вычисления выполняются независимо от потока программы, нет порядка, в котором они печатают свою информацию и заканчивают выполнение.</span><span class="sxs-lookup"><span data-stu-id="23a4b-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="23a4b-159">Вычисления будут запланированы параллельно, но их порядок выполнения не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="23a4b-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="23a4b-160">Последовательность асинхронных вычислений</span><span class="sxs-lookup"><span data-stu-id="23a4b-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="23a4b-161">Поскольку `Async<'T>` спецификация работы, а не уже запущенная задача, вы можете легко выполнять более сложные преобразования.</span><span class="sxs-lookup"><span data-stu-id="23a4b-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="23a4b-162">Вот пример, который последовательности набор вычислений Async, чтобы они выполняют один за другим.</span><span class="sxs-lookup"><span data-stu-id="23a4b-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="23a4b-163">Это будет `printTotalFileBytes` график для выполнения в `argv` порядке элементов, а не планирование их параллельно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="23a4b-164">Поскольку следующий элемент не будет запланирован до завершения выполнения последнего вычисления, вычисления секвенируются таким образом, что в их выполнении нет перекрытия.</span><span class="sxs-lookup"><span data-stu-id="23a4b-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="23a4b-165">Важные функции модуля Async</span><span class="sxs-lookup"><span data-stu-id="23a4b-165">Important Async module functions</span></span>

<span data-ttu-id="23a4b-166">Когда вы пишете код async в F,, вы обычно взаимодействуете с инфраструктурой, которая обрабатывает планирование вычислений для вас.</span><span class="sxs-lookup"><span data-stu-id="23a4b-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="23a4b-167">Однако, это не всегда так, так что это хорошо, чтобы узнать различные стартовые функции, чтобы запланировать асинхронную работу.</span><span class="sxs-lookup"><span data-stu-id="23a4b-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="23a4b-168">Поскольку асинхронные вычисления являются _спецификацией_ работы, а не представлением уже выполнения работы, они должны быть явно запущены с исходной функции.</span><span class="sxs-lookup"><span data-stu-id="23a4b-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="23a4b-169">Есть много [стартовых функций Async,](https://msdn.microsoft.com/library/ee370232.aspx) которые полезны в различных контекстах.</span><span class="sxs-lookup"><span data-stu-id="23a4b-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="23a4b-170">В следующем разделе описаны некоторые из наиболее распространенных стартовых функций.</span><span class="sxs-lookup"><span data-stu-id="23a4b-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="23a4b-171">Async.StartChild</span><span class="sxs-lookup"><span data-stu-id="23a4b-171">Async.StartChild</span></span>

<span data-ttu-id="23a4b-172">Запускает вычисление ребенка в рамках асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="23a4b-173">Это позволяет выполнять одновременно несколько асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="23a4b-174">Вычисление ребенка разделяет токен отмены с родительскими вычислениями.</span><span class="sxs-lookup"><span data-stu-id="23a4b-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="23a4b-175">Если родительские вычисления отменены, вычисления ребенка также отменяются.</span><span class="sxs-lookup"><span data-stu-id="23a4b-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="23a4b-176">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="23a4b-177">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-177">When to use:</span></span>

- <span data-ttu-id="23a4b-178">Если вы хотите выполнить несколько асинхронных вычислений одновременно, а не по одному за раз, но не планируется их параллельно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="23a4b-179">Если вы хотите связать срок службы детского вычисления с родительскими вычислениями.</span><span class="sxs-lookup"><span data-stu-id="23a4b-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="23a4b-180">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-180">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-181">Запуск нескольких вычислений `Async.StartChild` с не то же самое, что планировать их параллельно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="23a4b-182">Если вы хотите планировать вычисления параллельно, используйте `Async.Parallel`.</span><span class="sxs-lookup"><span data-stu-id="23a4b-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="23a4b-183">Отмена родительских вычислений вызовет отмену всех начатых ими детских вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="23a4b-184">Async.StartImmediate</span><span class="sxs-lookup"><span data-stu-id="23a4b-184">Async.StartImmediate</span></span>

<span data-ttu-id="23a4b-185">Запускает асинхронные вычисления, начиная сразу с текущего потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="23a4b-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="23a4b-186">Это полезно, если вам нужно обновить что-то на потоке вызова во время вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="23a4b-187">Например, если асинхронные вычисления должны обновлять ui (например, обновление панели прогресса), следует `Async.StartImmediate` использовать его.</span><span class="sxs-lookup"><span data-stu-id="23a4b-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="23a4b-188">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="23a4b-189">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-189">When to use:</span></span>

- <span data-ttu-id="23a4b-190">Когда вам нужно обновить что-то на потоке вызова в середине асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="23a4b-191">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-191">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-192">Код в асинхронных вычислениях будет работать на любом потоке, на который, случается, запланировано.</span><span class="sxs-lookup"><span data-stu-id="23a4b-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="23a4b-193">Это может быть проблематично, если этот поток каким-то образом чувствителен, например поток uI.</span><span class="sxs-lookup"><span data-stu-id="23a4b-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="23a4b-194">В таких `Async.StartImmediate` случаях, скорее всего, нецелесообразно использовать.</span><span class="sxs-lookup"><span data-stu-id="23a4b-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="23a4b-195">Async.StartasTask</span><span class="sxs-lookup"><span data-stu-id="23a4b-195">Async.StartAsTask</span></span>

<span data-ttu-id="23a4b-196">Выполняет вычисление в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="23a4b-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="23a4b-197"><xref:System.Threading.Tasks.Task%601> Возвращает, которая будет завершена в соответствующем состоянии после завершения вычислений (производит результат, выбрасывает исключение или отменяется).</span><span class="sxs-lookup"><span data-stu-id="23a4b-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="23a4b-198">Если токен отмены не предусмотрен, используется токен отмены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23a4b-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="23a4b-199">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="23a4b-200">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-200">When to use:</span></span>

- <span data-ttu-id="23a4b-201">При необходимости вызова API .NET, <xref:System.Threading.Tasks.Task%601> который ожидает, что будет представлен результат асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="23a4b-202">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-202">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-203">Этот вызов будет `Task` выделять дополнительный объект, который может увеличить накладные расходы, если он используется часто.</span><span class="sxs-lookup"><span data-stu-id="23a4b-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="23a4b-204">Async.Parallel</span><span class="sxs-lookup"><span data-stu-id="23a4b-204">Async.Parallel</span></span>

<span data-ttu-id="23a4b-205">Расписание последовательности асинхронных вычислений, которые должны выполняться параллельно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="23a4b-206">Степень параллелизма может быть дополнительно настроена/задушена `maxDegreesOfParallelism` путем указания параметра.</span><span class="sxs-lookup"><span data-stu-id="23a4b-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="23a4b-207">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="23a4b-208">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-208">When to use it:</span></span>

- <span data-ttu-id="23a4b-209">Если вам нужно запустить набор вычислений в то же время и не полагаться на их порядок выполнения.</span><span class="sxs-lookup"><span data-stu-id="23a4b-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="23a4b-210">Если вам не требуются результаты вычислений, запланированные параллельно, пока они не будут завершены.</span><span class="sxs-lookup"><span data-stu-id="23a4b-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="23a4b-211">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-211">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-212">Вы можете получить доступ к полученному массиву значений только после завершения всех вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="23a4b-213">Вычисления будут запущены, однако они в конечном итоге получить запланировано.</span><span class="sxs-lookup"><span data-stu-id="23a4b-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="23a4b-214">Это означает, что вы не можете полагаться на их порядок их исполнения.</span><span class="sxs-lookup"><span data-stu-id="23a4b-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="23a4b-215">Async.Последовательный</span><span class="sxs-lookup"><span data-stu-id="23a4b-215">Async.Sequential</span></span>

<span data-ttu-id="23a4b-216">Расписание последовательности асинхронных вычислений, которые должны быть выполнены в порядке, который они передаются.</span><span class="sxs-lookup"><span data-stu-id="23a4b-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="23a4b-217">Первые вычисления будут выполнены, затем следующий, и так далее.</span><span class="sxs-lookup"><span data-stu-id="23a4b-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="23a4b-218">Вычисления не выполняются параллельно.</span><span class="sxs-lookup"><span data-stu-id="23a4b-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="23a4b-219">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="23a4b-220">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-220">When to use it:</span></span>

- <span data-ttu-id="23a4b-221">Если вам нужно выполнить несколько вычислений в порядке.</span><span class="sxs-lookup"><span data-stu-id="23a4b-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="23a4b-222">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-222">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-223">Вы можете получить доступ к полученному массиву значений только после завершения всех вычислений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="23a4b-224">Вычисления будут выполняться в порядке, в котором они будут переданы этой функции, что может означать, что пройдет больше времени, прежде чем результаты будут возвращены.</span><span class="sxs-lookup"><span data-stu-id="23a4b-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="23a4b-225">Async.AwaitTask</span><span class="sxs-lookup"><span data-stu-id="23a4b-225">Async.AwaitTask</span></span>

<span data-ttu-id="23a4b-226">Возвращает асинхронные вычисления, которые <xref:System.Threading.Tasks.Task%601> ждут данного для завершения и возвращает свой результат в виде`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="23a4b-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="23a4b-227">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="23a4b-228">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-228">When to use:</span></span>

- <span data-ttu-id="23a4b-229">При потреблении API .NET, <xref:System.Threading.Tasks.Task%601> который возвращает asynchronous вычисления F's.</span><span class="sxs-lookup"><span data-stu-id="23a4b-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="23a4b-230">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-230">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-231">Исключения заворачиваются <xref:System.AggregateException> в соответствии с конвенцией Параллельной библиотеки задач, и это отличается от того, как F'async обычно всплывает на поверхность исключений.</span><span class="sxs-lookup"><span data-stu-id="23a4b-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="23a4b-232">Async.Catch</span><span class="sxs-lookup"><span data-stu-id="23a4b-232">Async.Catch</span></span>

<span data-ttu-id="23a4b-233">Создает асинхронные вычисления, которые `Async<'T>`выполняет `Async<Choice<'T, exn>>`данный, возвращая .</span><span class="sxs-lookup"><span data-stu-id="23a4b-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="23a4b-234">Если данное `Async<'T>` завершается успешно, `Choice1Of2` то a возвращается с резучным значением.</span><span class="sxs-lookup"><span data-stu-id="23a4b-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="23a4b-235">Если исключение выбрасывается до его завершения, то возврат исключиться `Choice2of2` с поднятым исключением.</span><span class="sxs-lookup"><span data-stu-id="23a4b-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="23a4b-236">Если он используется на асинхронных вычислениях, которые сами по себе состоят из многих вычислений, и один из этих вычислений бросает исключение, охватывающие вычисления будут полностью остановлены.</span><span class="sxs-lookup"><span data-stu-id="23a4b-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="23a4b-237">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="23a4b-238">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-238">When to use:</span></span>

- <span data-ttu-id="23a4b-239">При выполнении асинхронной работы, которая может выйти из строя за исключением, и вы хотите обрабатывать это исключение в вызываемом абоненте.</span><span class="sxs-lookup"><span data-stu-id="23a4b-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="23a4b-240">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-240">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-241">При использовании комбинированных или секвенированных асинхронных вычислений охватывающая вычисления полностью остановится, если один из его «внутренних» вычислений выбросит исключение.</span><span class="sxs-lookup"><span data-stu-id="23a4b-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="23a4b-242">Async.Ignore</span><span class="sxs-lookup"><span data-stu-id="23a4b-242">Async.Ignore</span></span>

<span data-ttu-id="23a4b-243">Создает асинхронные вычисления, которые выражает данный расчет и игнорируют его результат.</span><span class="sxs-lookup"><span data-stu-id="23a4b-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="23a4b-244">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="23a4b-245">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-245">When to use:</span></span>

- <span data-ttu-id="23a4b-246">Если у вас есть асинхронные вычисления, результат которых не нужен.</span><span class="sxs-lookup"><span data-stu-id="23a4b-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="23a4b-247">Это аналогично коду `ignore` неасинхронного кода.</span><span class="sxs-lookup"><span data-stu-id="23a4b-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="23a4b-248">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-248">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-249">Если вы должны использовать это, `Async.Start` потому что `Async<unit>`вы хотите использовать или другую функцию, которая требует, рассмотреть, если отбрасывание результат хорошо делать.</span><span class="sxs-lookup"><span data-stu-id="23a4b-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="23a4b-250">Отбрасывание результатов только для того, чтобы соответствовать подписи типа, как правило, не должно быть сделано.</span><span class="sxs-lookup"><span data-stu-id="23a4b-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="23a4b-251">Async.RunСинхронно</span><span class="sxs-lookup"><span data-stu-id="23a4b-251">Async.RunSynchronously</span></span>

<span data-ttu-id="23a4b-252">Запускает асинхронные вычисления и ждет его результата на потоке вызова.</span><span class="sxs-lookup"><span data-stu-id="23a4b-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="23a4b-253">Этот вызов блокируется.</span><span class="sxs-lookup"><span data-stu-id="23a4b-253">This call is blocking.</span></span>

<span data-ttu-id="23a4b-254">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="23a4b-255">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="23a4b-255">When to use it:</span></span>

- <span data-ttu-id="23a4b-256">Если вам это нужно, используйте его только один раз в приложении - в точке входа для исполняемой.</span><span class="sxs-lookup"><span data-stu-id="23a4b-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="23a4b-257">Если вы не заботитесь о производительности и хотите выполнить набор других асинхронных операций сразу.</span><span class="sxs-lookup"><span data-stu-id="23a4b-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="23a4b-258">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-258">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-259">Вызов `Async.RunSynchronously` блокирует поток вызова до завершения выполнения.</span><span class="sxs-lookup"><span data-stu-id="23a4b-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="23a4b-260">Async.Start</span><span class="sxs-lookup"><span data-stu-id="23a4b-260">Async.Start</span></span>

<span data-ttu-id="23a4b-261">Запускает асинхронные вычисления в пуле потоков, который возвращается. `unit`</span><span class="sxs-lookup"><span data-stu-id="23a4b-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="23a4b-262">Не ждет его результата.</span><span class="sxs-lookup"><span data-stu-id="23a4b-262">Doesn't wait for its result.</span></span> <span data-ttu-id="23a4b-263">Вложенные вычисления, `Async.Start` начатые с запуска, запускаются полностью независимо от родительских вычислений, которые их называли.</span><span class="sxs-lookup"><span data-stu-id="23a4b-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="23a4b-264">Их продолжительность жизни не привязана ни к какому родительскому вычислению.</span><span class="sxs-lookup"><span data-stu-id="23a4b-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="23a4b-265">Если родительские вычисления отменены, не отменяются детские вычисления.</span><span class="sxs-lookup"><span data-stu-id="23a4b-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="23a4b-266">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="23a4b-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="23a4b-267">Используйте только тогда, когда:</span><span class="sxs-lookup"><span data-stu-id="23a4b-267">Use only when:</span></span>

- <span data-ttu-id="23a4b-268">У вас есть асинхронные вычисления, которые не дают результата и/или требуют его обработки.</span><span class="sxs-lookup"><span data-stu-id="23a4b-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="23a4b-269">Вам не нужно знать, когда асинхронные вычисления завершены.</span><span class="sxs-lookup"><span data-stu-id="23a4b-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="23a4b-270">Вам все равно, на какой поток работает асинхронная вычисления.</span><span class="sxs-lookup"><span data-stu-id="23a4b-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="23a4b-271">У вас нет необходимости быть в курсе или сообщать об исключениях, вытекающих из задачи.</span><span class="sxs-lookup"><span data-stu-id="23a4b-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="23a4b-272">На что обратить сяочку:</span><span class="sxs-lookup"><span data-stu-id="23a4b-272">What to watch out for:</span></span>

- <span data-ttu-id="23a4b-273">Исключения, поднятые вычислениями, `Async.Start` начатыми с, не распространяются на вызыватель.</span><span class="sxs-lookup"><span data-stu-id="23a4b-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="23a4b-274">Стек вызова будет полностью развёрнут.</span><span class="sxs-lookup"><span data-stu-id="23a4b-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="23a4b-275">Любая эффективная работа `printfn`(например, вызов), начатая с `Async.Start` не приведет к тому, что эффект может произойти на основной поток выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="23a4b-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="23a4b-276">Взаимодействие с .NET</span><span class="sxs-lookup"><span data-stu-id="23a4b-276">Interoperate with .NET</span></span>

<span data-ttu-id="23a4b-277">Возможно, вы работаете с библиотекой .NET или базой кода с c'net, которая использует асинхронное программирование в стиле [async/await.](../../../standard/async.md)</span><span class="sxs-lookup"><span data-stu-id="23a4b-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="23a4b-278">Поскольку в качестве основных абстракций и <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> типов используется `Async<'T>`c-образная система, а не , необходимо пересечь границу между этими двумя подходами к асинхронности.</span><span class="sxs-lookup"><span data-stu-id="23a4b-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="23a4b-279">Как работать с .NET async и`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="23a4b-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="23a4b-280">Работа с библиотеками async .NET <xref:System.Threading.Tasks.Task%601> и базами кода, которые используют (т.е. вычислениями async, которые имеют значения возврата), является простой и имеет встроенную поддержку с F..</span><span class="sxs-lookup"><span data-stu-id="23a4b-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="23a4b-281">Функция может `Async.AwaitTask` использоваться для ожидания асинхронных вычислений .NET:</span><span class="sxs-lookup"><span data-stu-id="23a4b-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="23a4b-282">Функцию `Async.StartAsTask` можно использовать для передачи асинхронных вычислений вызывающему абоненту .NET:</span><span class="sxs-lookup"><span data-stu-id="23a4b-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="23a4b-283">Как работать с .NET async и`Task`</span><span class="sxs-lookup"><span data-stu-id="23a4b-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="23a4b-284">Для работы с <xref:System.Threading.Tasks.Task> AI, которые используют (т.е. вычисления .NET async, которые не возвращают `Async<'T>` значение), <xref:System.Threading.Tasks.Task>может потребоваться добавить дополнительную функцию, которая преобразует ся:</span><span class="sxs-lookup"><span data-stu-id="23a4b-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="23a4b-285">Существует уже, `Async.AwaitTask` что принимает <xref:System.Threading.Tasks.Task> в качестве ввода.</span><span class="sxs-lookup"><span data-stu-id="23a4b-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="23a4b-286">С помощью этой `startTaskFromAsyncUnit` и ранее определенной <xref:System.Threading.Tasks.Task> функции можно начать и ждать типы из вычислений F'async.</span><span class="sxs-lookup"><span data-stu-id="23a4b-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="23a4b-287">Отношение к многопоточному</span><span class="sxs-lookup"><span data-stu-id="23a4b-287">Relationship to multi-threading</span></span>

<span data-ttu-id="23a4b-288">Хотя потоки упоминается в этой статье, Есть две важные вещи, чтобы помнить:</span><span class="sxs-lookup"><span data-stu-id="23a4b-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="23a4b-289">Нет никакого сродства между асинхронным вычислением и потоком, если только явно не запущенный на текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="23a4b-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="23a4b-290">Асинхронное программирование в F- не является абстракцией для многопоточности.</span><span class="sxs-lookup"><span data-stu-id="23a4b-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="23a4b-291">Например, вычисление может фактически работать на потоке вызывающего абонента, в зависимости от характера работы.</span><span class="sxs-lookup"><span data-stu-id="23a4b-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="23a4b-292">Вычисление может также "прыгать" между потоками, заимствуя их на небольшое количество времени, чтобы сделать полезную работу между периодами "ожидания" (например, когда сетевой вызов находится в пути).</span><span class="sxs-lookup"><span data-stu-id="23a4b-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="23a4b-293">Хотя F-образное взаимодействие дает некоторые возможности для запуска асинхронных вычислений на текущем потоке (или явно не в текущем потоке), асинхронность обычно не связана с конкретной стратегией потоков.</span><span class="sxs-lookup"><span data-stu-id="23a4b-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="23a4b-294">См. также</span><span class="sxs-lookup"><span data-stu-id="23a4b-294">See also</span></span>

- [<span data-ttu-id="23a4b-295">Модель асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="23a4b-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="23a4b-296">Jet.com в F е Async Руководство</span><span class="sxs-lookup"><span data-stu-id="23a4b-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="23a4b-297">F для удовольствия и прибыли асинхронного программирования руководство</span><span class="sxs-lookup"><span data-stu-id="23a4b-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="23a4b-298">Асинхрон в C и F: Асинхронные gotchas в C #</span><span class="sxs-lookup"><span data-stu-id="23a4b-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
