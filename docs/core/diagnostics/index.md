---
title: Общие сведения о средствах диагностики в .NET Core
description: Общие сведения о средствах и методах диагностики приложений .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: ae3b9a1961f331c9cdea786bd5fe06b7bfa10927
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558118"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="d2fe1-103">Общие сведения о средствах диагностики в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d2fe1-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="d2fe1-104">Программное обеспечение не всегда работает должным образом, но в .NET Core есть средства и API, которые помогут вам быстро и эффективно диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="d2fe1-105">Эта статья поможет вам выбрать нужные средства.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="d2fe1-106">Управляемые отладчики</span><span class="sxs-lookup"><span data-stu-id="d2fe1-106">Managed debuggers</span></span>

<span data-ttu-id="d2fe1-107">[Управляемые отладчики](managed-debuggers.md) позволяют взаимодействовать с программой.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="d2fe1-108">Такие операции, как приостановка, инкрементное выполнение, анализ и возобновление, предоставляют сведения о поведении кода.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="d2fe1-109">Отладчик — это самое подходящее средство для диагностики функциональных проблем, которые можно легко воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="d2fe1-110">Ведение журнала и трассировка</span><span class="sxs-lookup"><span data-stu-id="d2fe1-110">Logging and tracing</span></span>

<span data-ttu-id="d2fe1-111">[Ведение журнала и трассировка](logging-tracing.md) — это связанные методы,</span><span class="sxs-lookup"><span data-stu-id="d2fe1-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="d2fe1-112">предназначенные для инструментирования кода и создания файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="d2fe1-113">В файлах записываются сведения о том, что делает программа.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-113">The files record the details of what a program does.</span></span> <span data-ttu-id="d2fe1-114">Эти сведения можно использовать для диагностики самых сложных проблем.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="d2fe1-115">В сочетании с метками времени эти методы также используются для выявления проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="d2fe1-116">Модульное тестирование</span><span class="sxs-lookup"><span data-stu-id="d2fe1-116">Unit testing</span></span>

<span data-ttu-id="d2fe1-117">[Модульное тестирование](../testing/index.md) — это ключевой компонент непрерывной интеграции и развертывания высококачественного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="d2fe1-118">Модульные тесты позволяют сразу же узнать о возникшей проблеме.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="d2fe1-119">Глобальные средства диагностики dotnet в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d2fe1-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="d2fe1-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="d2fe1-120">dotnet-counters</span></span>

<span data-ttu-id="d2fe1-121">[dotnet-counters](dotnet-counters.md) — это средство мониторинга производительности для первого уровня мониторинга работоспособности и анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="d2fe1-122">Оно отслеживает значения счетчиков производительности, опубликованные с помощью API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="d2fe1-123">Например, можно быстро отслеживать использование ЦП или частоту возникновения исключений в приложении .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="d2fe1-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="d2fe1-124">dotnet-dump</span></span>

<span data-ttu-id="d2fe1-125">[dotnet-dump](dotnet-dump.md) — это средство сбора и анализа дампов ядра Windows и Linux без собственного отладчика.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="d2fe1-126">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="d2fe1-126">dotnet-gcdump</span></span>

<span data-ttu-id="d2fe1-127">Средство [dotnet-gcdump](dotnet-gcdump.md) предоставляет способ сбора дампов сборщика мусора (GC) для активных процессов .NET.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-127">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="d2fe1-128">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d2fe1-128">dotnet-trace</span></span>

<span data-ttu-id="d2fe1-129">.NET Core включает в себя `EventPipe`, с помощью которого предоставляются диагностические данные.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-129">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="d2fe1-130">Средство [dotnet-trace](dotnet-trace.md) позволяет использовать интересные данные профилирования из приложения, которые могут помочь в сценариях, когда вам нужно найти причину медленной работы приложений.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-130">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="d2fe1-131">Учебники по диагностике .NET Core</span><span class="sxs-lookup"><span data-stu-id="d2fe1-131">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="d2fe1-132">Отладка утечек памяти</span><span class="sxs-lookup"><span data-stu-id="d2fe1-132">Debug a memory leak</span></span>

<span data-ttu-id="d2fe1-133">[Учебник. Отладка утечек памяти](debug-memory-leak.md) содержит пошаговые инструкции по поиску утечек памяти.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-133">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="d2fe1-134">Средство [dotnet-counters](dotnet-counters.md) позволяет подтвердить наличие утечки, а средство [dotnet-dump](dotnet-dump.md) используется для ее диагностики.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-134">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="d2fe1-135">Отладка высокой загрузки ЦП</span><span class="sxs-lookup"><span data-stu-id="d2fe1-135">Debug high CPU usage</span></span>

<span data-ttu-id="d2fe1-136">В [руководстве по отладке высокой загрузки ЦП](debug-highcpu.md) приводятся пошаговые инструкции по изучению высокой загрузки ЦП.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-136">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="d2fe1-137">Для подтверждения высокой загрузки ЦП используется средство [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d2fe1-137">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="d2fe1-138">Затем вы узнаете, как использовать [служебную программу трассировки для анализа производительности (`dotnet-trace`)](dotnet-trace.md) или `perf` для Linux, чтобы получить и просмотреть профиль загрузки ЦП.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-138">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="d2fe1-139">Отладка взаимоблокировки</span><span class="sxs-lookup"><span data-stu-id="d2fe1-139">Debug deadlock</span></span>

<span data-ttu-id="d2fe1-140">В [руководстве по отладке взаимоблокировки](debug-deadlock.md) показано, как использовать средство [dotnet-dump](dotnet-dump.md) для изучения потоков и блокировок.</span><span class="sxs-lookup"><span data-stu-id="d2fe1-140">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
