---
title: Общие сведения о средствах диагностики в .NET Core
description: Общие сведения о средствах и методах диагностики приложений .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: c43e661ad8c9f665151e0240bf6b54e61b9acfef
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031921"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="77c1c-103">Общие сведения о средствах диагностики в .NET Core</span><span class="sxs-lookup"><span data-stu-id="77c1c-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="77c1c-104">Программное обеспечение не всегда работает должным образом, но в .NET Core есть средства и API, которые помогут вам быстро и эффективно диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="77c1c-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="77c1c-105">Эта статья поможет вам выбрать нужные средства.</span><span class="sxs-lookup"><span data-stu-id="77c1c-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="77c1c-106">Управляемые отладчики</span><span class="sxs-lookup"><span data-stu-id="77c1c-106">Managed debuggers</span></span>

<span data-ttu-id="77c1c-107">[Управляемые отладчики](managed-debuggers.md) позволяют взаимодействовать с программой.</span><span class="sxs-lookup"><span data-stu-id="77c1c-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="77c1c-108">Такие операции, как приостановка, инкрементное выполнение, анализ и возобновление, предоставляют сведения о поведении кода.</span><span class="sxs-lookup"><span data-stu-id="77c1c-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="77c1c-109">Отладчик — это самое подходящее средство для диагностики функциональных проблем, которые можно легко воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="77c1c-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="77c1c-110">Ведение журнала и трассировка</span><span class="sxs-lookup"><span data-stu-id="77c1c-110">Logging and tracing</span></span>

<span data-ttu-id="77c1c-111">[Ведение журнала и трассировка](logging-tracing.md) — это связанные методы,</span><span class="sxs-lookup"><span data-stu-id="77c1c-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="77c1c-112">предназначенные для инструментирования кода и создания файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="77c1c-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="77c1c-113">В файлах записываются сведения о том, что делает программа.</span><span class="sxs-lookup"><span data-stu-id="77c1c-113">The files record the details of what a program does.</span></span> <span data-ttu-id="77c1c-114">Эти сведения можно использовать для диагностики самых сложных проблем.</span><span class="sxs-lookup"><span data-stu-id="77c1c-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="77c1c-115">В сочетании с метками времени эти методы также используются для выявления проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="77c1c-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="77c1c-116">Модульное тестирование</span><span class="sxs-lookup"><span data-stu-id="77c1c-116">Unit testing</span></span>

<span data-ttu-id="77c1c-117">[Модульное тестирование](../testing/index.md) — это ключевой компонент непрерывной интеграции и развертывания высококачественного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="77c1c-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="77c1c-118">Модульные тесты позволяют сразу же узнать о возникшей проблеме.</span><span class="sxs-lookup"><span data-stu-id="77c1c-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="dumps"></a><span data-ttu-id="77c1c-119">Файлы дампа</span><span class="sxs-lookup"><span data-stu-id="77c1c-119">Dumps</span></span>

<span data-ttu-id="77c1c-120">[Дамп](./dumps.md) — это файл, содержащий моментальный снимок процесса во время создания.</span><span class="sxs-lookup"><span data-stu-id="77c1c-120">A [dump](./dumps.md) is a file that contains a snapshot of the process at the time of creation.</span></span> <span data-ttu-id="77c1c-121">Он может использоваться при проверке состояния приложения для отладки.</span><span class="sxs-lookup"><span data-stu-id="77c1c-121">These can be useful for examining the state of your application for debugging purposes.</span></span>

## <a name="collect-diagnostics-in-containers"></a><span data-ttu-id="77c1c-122">Сбор диагностики в контейнерах</span><span class="sxs-lookup"><span data-stu-id="77c1c-122">Collect diagnostics in containers</span></span>

<span data-ttu-id="77c1c-123">Средства диагностики, используемые в средах Linux без контейнеров, позволяют также осуществлять и [сбор диагностики в контейнерах](diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="77c1c-123">The same diagnostics tools that are used in non-containerized Linux environments can also be used to [collect diagnostics in containers](diagnostics-in-containers.md).</span></span> <span data-ttu-id="77c1c-124">Требуется лишь частично изменить использование, чтобы обеспечить работу этих средств в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="77c1c-124">There are just a few usage changes needed to make sure the tools work in a Docker container.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="77c1c-125">Отладка дампов Linux</span><span class="sxs-lookup"><span data-stu-id="77c1c-125">Debug Linux dumps</span></span>

<span data-ttu-id="77c1c-126">[Отладка дампов Linux](debug-linux-dumps.md) — узнайте, как собирать и анализировать дампы в Linux.</span><span class="sxs-lookup"><span data-stu-id="77c1c-126">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="77c1c-127">Глобальные средства диагностики в .NET Core</span><span class="sxs-lookup"><span data-stu-id="77c1c-127">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="77c1c-128">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="77c1c-128">dotnet-counters</span></span>

<span data-ttu-id="77c1c-129">[dotnet-counters](dotnet-counters.md) — это средство мониторинга производительности для первого уровня мониторинга работоспособности и анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="77c1c-129">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="77c1c-130">Оно отслеживает значения счетчиков производительности, опубликованные с помощью API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="77c1c-130">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="77c1c-131">Например, можно быстро отслеживать использование ЦП или частоту возникновения исключений в приложении .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77c1c-131">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="77c1c-132">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="77c1c-132">dotnet-dump</span></span>

<span data-ttu-id="77c1c-133">[dotnet-dump](dotnet-dump.md) — это средство сбора и анализа дампов ядра Windows и Linux без собственного отладчика.</span><span class="sxs-lookup"><span data-stu-id="77c1c-133">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="77c1c-134">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="77c1c-134">dotnet-gcdump</span></span>

<span data-ttu-id="77c1c-135">Средство [dotnet-gcdump](dotnet-gcdump.md) предоставляет способ сбора дампов сборщика мусора (GC) для активных процессов .NET.</span><span class="sxs-lookup"><span data-stu-id="77c1c-135">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="77c1c-136">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="77c1c-136">dotnet-trace</span></span>

<span data-ttu-id="77c1c-137">.NET Core включает в себя `EventPipe`, с помощью которого предоставляются диагностические данные.</span><span class="sxs-lookup"><span data-stu-id="77c1c-137">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="77c1c-138">Средство [dotnet-trace](dotnet-trace.md) позволяет использовать интересные данные профилирования из приложения, которые могут помочь в сценариях, когда вам нужно найти причину медленной работы приложений.</span><span class="sxs-lookup"><span data-stu-id="77c1c-138">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="77c1c-139">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="77c1c-139">dotnet-symbol</span></span>

<span data-ttu-id="77c1c-140">[dotnet-symbol](dotnet-symbol.md) скачивает файлы (символы, DAC/DBI, файлы узлов и т. д.), требуемые для открытия основного дампа или минидампа.</span><span class="sxs-lookup"><span data-stu-id="77c1c-140">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="77c1c-141">Используйте это средство, если для отладки файла дампа, записанного на другом компьютере, требуются символы и модули.</span><span class="sxs-lookup"><span data-stu-id="77c1c-141">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="77c1c-142">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="77c1c-142">dotnet-sos</span></span>

<span data-ttu-id="77c1c-143">[dotnet-sos](dotnet-sos.md) используется для установки [расширения отладки SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) в Linux или MacOS (или в Windows при использовании старых средств отладки).</span><span class="sxs-lookup"><span data-stu-id="77c1c-143">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

### <a name="perfcollect"></a><span data-ttu-id="77c1c-144">PerfCollect</span><span class="sxs-lookup"><span data-stu-id="77c1c-144">PerfCollect</span></span>

<span data-ttu-id="77c1c-145">[PerfCollect](trace-perfcollect-lttng.md) — это скрипт bash, который можно использовать для сбора трассировок с помощью `perf` и `LTTng` для подробного анализа производительности приложений .NET, выполняющихся в дистрибутивах Linux.</span><span class="sxs-lookup"><span data-stu-id="77c1c-145">[PerfCollect](trace-perfcollect-lttng.md) is a bash script you can use to collect traces with `perf` and `LTTng` for a more in-depth performance analysis of .NET apps running on Linux distributions.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="77c1c-146">Учебники по диагностике .NET Core</span><span class="sxs-lookup"><span data-stu-id="77c1c-146">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="77c1c-147">Отладка утечек памяти</span><span class="sxs-lookup"><span data-stu-id="77c1c-147">Debug a memory leak</span></span>

<span data-ttu-id="77c1c-148">[Учебник. Отладка утечек памяти](debug-memory-leak.md) содержит пошаговые инструкции по поиску утечек памяти.</span><span class="sxs-lookup"><span data-stu-id="77c1c-148">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="77c1c-149">Средство [dotnet-counters](dotnet-counters.md) позволяет подтвердить наличие утечки, а средство [dotnet-dump](dotnet-dump.md) используется для ее диагностики.</span><span class="sxs-lookup"><span data-stu-id="77c1c-149">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="77c1c-150">Отладка высокой загрузки ЦП</span><span class="sxs-lookup"><span data-stu-id="77c1c-150">Debug high CPU usage</span></span>

<span data-ttu-id="77c1c-151">В [руководстве по отладке высокой загрузки ЦП](debug-highcpu.md) приводятся пошаговые инструкции по изучению высокой загрузки ЦП.</span><span class="sxs-lookup"><span data-stu-id="77c1c-151">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="77c1c-152">Для подтверждения высокой загрузки ЦП используется средство [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="77c1c-152">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="77c1c-153">Затем вы узнаете, как использовать [служебную программу трассировки для анализа производительности (`dotnet-trace`)](dotnet-trace.md) или `perf` для Linux, чтобы получить и просмотреть профиль загрузки ЦП.</span><span class="sxs-lookup"><span data-stu-id="77c1c-153">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="77c1c-154">Отладка взаимоблокировки</span><span class="sxs-lookup"><span data-stu-id="77c1c-154">Debug deadlock</span></span>

<span data-ttu-id="77c1c-155">В [руководстве по отладке взаимоблокировки](debug-deadlock.md) показано, как использовать средство [dotnet-dump](dotnet-dump.md) для изучения потоков и блокировок.</span><span class="sxs-lookup"><span data-stu-id="77c1c-155">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>

### <a name="measure-performance-using-eventcounters"></a><span data-ttu-id="77c1c-156">Измерение производительности с помощью EventCounters</span><span class="sxs-lookup"><span data-stu-id="77c1c-156">Measure performance using EventCounters</span></span>

<span data-ttu-id="77c1c-157">[Учебник. Измерение производительности с помощью EventCounters в .NET](event-counter-perf.md) демонстрирует, как использовать API <xref:System.Diagnostics.Tracing.EventCounter> для измерения производительности в приложении .NET.</span><span class="sxs-lookup"><span data-stu-id="77c1c-157">[Tutorial: Measure performance using EventCounters in .NET](event-counter-perf.md) shows you how to use the <xref:System.Diagnostics.Tracing.EventCounter> API to measure performance in your .NET app.</span></span>
