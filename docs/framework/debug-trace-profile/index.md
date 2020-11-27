---
title: Отладка, трассировка и профилирование
description: Сведения об отладке, трассировке и профилировании в .NET. См. статьи, посвященные JIT-отладке, трассировке и инструментированию приложений и многое другое.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
ms.openlocfilehash: 33dd840f4c1421bbff54499af56ab3e147cc694b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272778"
---
# <a name="debugging-tracing-and-profiling"></a><span data-ttu-id="86a44-104">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="86a44-104">Debugging, Tracing, and Profiling</span></span>

<span data-ttu-id="86a44-105">Для отладки приложения .NET Framework компилятор и среда выполнения должны быть настроены для включения присоединения отладчика к приложению и создания символов и сопоставлений строк, если это возможно, для приложения и его соответствующего языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="86a44-105">To debug a .NET Framework application, the compiler and runtime environment must be configured to enable a debugger to attach to the application and to produce both symbols and line maps, if possible, for the application and its corresponding Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="86a44-106">После отладки управляемого приложения можно выполнить его профилирование для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="86a44-106">After a managed application has been debugged, it can be profiled to boost performance.</span></span> <span data-ttu-id="86a44-107">Профилирование оценивает и описывает строки исходного кода, создающие наиболее часто выполняемый код, и время, необходимое для их выполнения.</span><span class="sxs-lookup"><span data-stu-id="86a44-107">Profiling evaluates and describes the lines of source code that generate the most frequently executed code, and how much time it takes to execute them.</span></span>  
  
 <span data-ttu-id="86a44-108">Приложения .NET Framework можно легко отладить с помощью Visual Studio, который обрабатывает многие детали конфигурации.</span><span class="sxs-lookup"><span data-stu-id="86a44-108">.NET Framework applications are easily debugged by using Visual Studio, which handles many of the configuration details.</span></span> <span data-ttu-id="86a44-109">Если Visual Studio не установлен, вы можете проверять и улучшать производительность приложений .NET Framework с помощью классов отладки в пространстве имен <xref:System.Diagnostics> .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86a44-109">If Visual Studio is not installed, you can examine and improve the performance of .NET Framework applications by using the debugging classes in the .NET Framework <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="86a44-110">Это пространство имен включает классы <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.TraceSource> для трассировки потока выполнения и классы <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> и <xref:System.Diagnostics.PerformanceCounter> для профилирования кода.</span><span class="sxs-lookup"><span data-stu-id="86a44-110">This namespace includes the <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug>, and <xref:System.Diagnostics.TraceSource> classes for tracing execution flow, and the <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog>, and <xref:System.Diagnostics.PerformanceCounter> classes for profiling code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86a44-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="86a44-111">In This Section</span></span>  

 [<span data-ttu-id="86a44-112">Включение отладки с JIT-присоединением (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="86a44-112">Enabling JIT-Attach Debugging</span></span>](enabling-jit-attach-debugging.md)  
 <span data-ttu-id="86a44-113">Показывается, как настроить реестр для JIT-присоединения модуля отладки к приложению .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86a44-113">Shows how to configure the registry to JIT-attach a debug engine to a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="86a44-114">Упрощение отладки образов</span><span class="sxs-lookup"><span data-stu-id="86a44-114">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)  
 <span data-ttu-id="86a44-115">Показывается, как включить отслеживание JIT и отключить оптимизацию для упрощения процесса отладки сборки.</span><span class="sxs-lookup"><span data-stu-id="86a44-115">Shows how to turn JIT tracking on and optimization off to make an assembly easier to debug.</span></span>  
  
 [<span data-ttu-id="86a44-116">Трассировка и инструментирование приложений</span><span class="sxs-lookup"><span data-stu-id="86a44-116">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)  
 <span data-ttu-id="86a44-117">Описывается, как наблюдать за приложением, пока оно выполняется, и как инструментировать его для отображения того, насколько оно хорошо работает, или того, что пошло не так.</span><span class="sxs-lookup"><span data-stu-id="86a44-117">Describes how to monitor the execution of your application while it is running, and how to instrument it to display how well it is performing or whether something has gone wrong.</span></span>  
  
 [<span data-ttu-id="86a44-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="86a44-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)  
 <span data-ttu-id="86a44-119">Сведения о помощниках по отладке управляемого кода (MDA), которые являются вспомогательными средствами отладки, работающими совместно со средой CLR для предоставления сведений о состоянии времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="86a44-119">Describes managed debugging assistants (MDAs), which are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span>  
  
 [<span data-ttu-id="86a44-120">Повышение эффективности отладки с помощью атрибутов просмотра отладчика</span><span class="sxs-lookup"><span data-stu-id="86a44-120">Enhancing Debugging with the Debugger Display Attributes</span></span>](enhancing-debugging-with-the-debugger-display-attributes.md)  
 <span data-ttu-id="86a44-121">Описывается, как разработчик типа может указать, как этот тип будет выглядеть при отображении в отладчике.</span><span class="sxs-lookup"><span data-stu-id="86a44-121">Describes how the developer of a type can specify what that type will look like when it is displayed in a debugger.</span></span>  
  
 [<span data-ttu-id="86a44-122">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="86a44-122">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="86a44-123">Описываются счетчики, которые можно использовать для отслеживания производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="86a44-123">Describes the counters that you can use to track the performance of an application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="86a44-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="86a44-124">Related Sections</span></span>  

 [<span data-ttu-id="86a44-125">Отладка приложений ASP.NET и ASP.NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86a44-125">Debug ASP.NET or ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)  
 <span data-ttu-id="86a44-126">Предоставляются предварительные требования и инструкции по отладке приложения ASP.NET во время разработки или после развертывания.</span><span class="sxs-lookup"><span data-stu-id="86a44-126">Provides prerequisites and instructions for how to debug an ASP.NET application during development or after deployment.</span></span>  
  
 [<span data-ttu-id="86a44-127">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="86a44-127">Development Guide</span></span>](../development-guide.md)  
 <span data-ttu-id="86a44-128">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="86a44-128">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
