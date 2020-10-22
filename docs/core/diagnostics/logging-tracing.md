---
title: Ведение журнала и трассировка (.NET Core)
description: Общие сведения о ведении журнала и трассировке в .NET Core.
ms.date: 10/12/2020
ms.openlocfilehash: 33c78ecc839b552267ad43dd00b7d627e756a939
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997704"
---
# <a name="net-core-logging-and-tracing"></a><span data-ttu-id="79ebe-103">Ведение журнала и трассировка в .NET Core</span><span class="sxs-lookup"><span data-stu-id="79ebe-103">.NET Core logging and tracing</span></span>

<span data-ttu-id="79ebe-104">Термины "ведение журнала" и "трассировка" по сути обозначают одну и ту же методику.</span><span class="sxs-lookup"><span data-stu-id="79ebe-104">Logging and tracing are really two names for the same technique.</span></span> <span data-ttu-id="79ebe-105">Этот простой метод отладки появился одновременно с первыми компьютерами.</span><span class="sxs-lookup"><span data-stu-id="79ebe-105">The simple technique has been used since the early days of computers.</span></span> <span data-ttu-id="79ebe-106">Он подразумевает создание в приложении средств для сохранения выходных данных, которые будут использоваться позднее.</span><span class="sxs-lookup"><span data-stu-id="79ebe-106">It simply involves instrumenting an application to write output to be consumed later.</span></span>

## <a name="reasons-to-use-logging-and-tracing"></a><span data-ttu-id="79ebe-107">Причины для трассировки и ведения журнала</span><span class="sxs-lookup"><span data-stu-id="79ebe-107">Reasons to use logging and tracing</span></span>

<span data-ttu-id="79ebe-108">Этот простой прием является удивительно эффективным.</span><span class="sxs-lookup"><span data-stu-id="79ebe-108">This simple technique is surprisingly powerful.</span></span> <span data-ttu-id="79ebe-109">Его можно использовать в ситуациях, с которыми не справляется отладчик.</span><span class="sxs-lookup"><span data-stu-id="79ebe-109">It can be used in situations where a debugger fails:</span></span>

- <span data-ttu-id="79ebe-110">Проблемы, возникающие в течение длительного периода, часто трудно устранять в традиционном отладчике.</span><span class="sxs-lookup"><span data-stu-id="79ebe-110">Issues occurring over long periods of time, can be difficult to debug with a traditional debugger.</span></span> <span data-ttu-id="79ebe-111">Журналы позволяют выполнять подробный анализ после проявления проблем, накопившихся за длительный период.</span><span class="sxs-lookup"><span data-stu-id="79ebe-111">Logs allow for detailed post-mortem review spanning long periods of time.</span></span> <span data-ttu-id="79ebe-112">В отладчиках, напротив, доступен лишь анализ в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="79ebe-112">In contrast, debuggers are constrained to real-time analysis.</span></span>
- <span data-ttu-id="79ebe-113">Многопоточные приложения и распределенные приложения часто трудно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="79ebe-113">Multi-threaded applications and distributed applications are often difficult to debug.</span></span>  <span data-ttu-id="79ebe-114">Присоединение отладчика часто изменяет поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="79ebe-114">Attaching a debugger tends to modify behaviors.</span></span> <span data-ttu-id="79ebe-115">Подробные журналы можно изучать по мере необходимости для анализа сложных систем.</span><span class="sxs-lookup"><span data-stu-id="79ebe-115">Detailed logs can be analyzed as needed to understand complex systems.</span></span>
- <span data-ttu-id="79ebe-116">Проблемы в распределенных приложениях могут возникать из-за сложностей взаимодействия между многими компонентами, а подключение отладчика к каждой части системы неоправданно усложняет процесс.</span><span class="sxs-lookup"><span data-stu-id="79ebe-116">Issues in distributed applications may arise from a complex interaction between many components and it may not be reasonable to connect a debugger to every part of the system.</span></span>
- <span data-ttu-id="79ebe-117">Многие службы нельзя останавливать.</span><span class="sxs-lookup"><span data-stu-id="79ebe-117">Many services shouldn't be stalled.</span></span> <span data-ttu-id="79ebe-118">Присоединение отладчика часто приводит к превышению времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="79ebe-118">Attaching a debugger often causes timeout failures.</span></span>
- <span data-ttu-id="79ebe-119">Проблемы не всегда удается прогнозировать.</span><span class="sxs-lookup"><span data-stu-id="79ebe-119">Issues aren't always foreseen.</span></span> <span data-ttu-id="79ebe-120">Ведение журнала и трассировка создают очень низкую нагрузку, поэтому программы будут сохранять данные даже при возникновении проблемы.</span><span class="sxs-lookup"><span data-stu-id="79ebe-120">Logging and tracing are designed for low overhead so that programs can always be recording in case an issue occurs.</span></span>

## <a name="net-core-apis"></a><span data-ttu-id="79ebe-121">API-интерфейсы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="79ebe-121">.NET Core APIs</span></span>

### <a name="print-style-apis"></a><span data-ttu-id="79ebe-122">API стиля печати</span><span class="sxs-lookup"><span data-stu-id="79ebe-122">Print style APIs</span></span>

<span data-ttu-id="79ebe-123">Классы <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> и <xref:System.Diagnostics.Debug?displayProperty=nameWithType> предоставляют похожие API-интерфейсы стиля печати, удобные для ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="79ebe-123">The <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes each provide similar print style APIs convenient for logging.</span></span>

<span data-ttu-id="79ebe-124">Вы можете выбрать любой из этих API стиля печати.</span><span class="sxs-lookup"><span data-stu-id="79ebe-124">The choice of which print style API to use is up to you.</span></span> <span data-ttu-id="79ebe-125">Основные отличия указаны далее.</span><span class="sxs-lookup"><span data-stu-id="79ebe-125">The key differences are:</span></span>

- <xref:System.Console?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-126">Всегда включен и всегда записывает данные в консоль.</span><span class="sxs-lookup"><span data-stu-id="79ebe-126">Always enabled and always writes to the console.</span></span>
  - <span data-ttu-id="79ebe-127">Полезно для сведений, которые могут потребоваться клиенту для просмотра в выпуске.</span><span class="sxs-lookup"><span data-stu-id="79ebe-127">Useful for information that your customer may need to see in the release.</span></span>
  - <span data-ttu-id="79ebe-128">Это самый простой подход. Он часто используется для краткосрочных и непредвиденных действий по отладке.</span><span class="sxs-lookup"><span data-stu-id="79ebe-128">Because it's the simplest approach, it's often used for ad-hoc temporary debugging.</span></span> <span data-ttu-id="79ebe-129">Такой код отладки часто даже не попадает в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="79ebe-129">This debug code is often never checked in to source control.</span></span>
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-130">Включается только при наличии определения `TRACE`.</span><span class="sxs-lookup"><span data-stu-id="79ebe-130">Only enabled when `TRACE` is defined.</span></span>
  - <span data-ttu-id="79ebe-131">Записывает данные в присоединенные прослушиватели (<xref:System.Diagnostics.Trace.Listeners>, по умолчанию это <xref:System.Diagnostics.DefaultTraceListener>).</span><span class="sxs-lookup"><span data-stu-id="79ebe-131">Writes to attached <xref:System.Diagnostics.Trace.Listeners>, by default the <xref:System.Diagnostics.DefaultTraceListener>.</span></span>
  - <span data-ttu-id="79ebe-132">Используйте этот API при создании журналов, которые будут включены в большинстве сборок.</span><span class="sxs-lookup"><span data-stu-id="79ebe-132">Use this API when creating logs that will be enabled in most builds.</span></span>
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-133">Включается только при наличии определения `DEBUG`.</span><span class="sxs-lookup"><span data-stu-id="79ebe-133">Only enabled when `DEBUG` is defined.</span></span>
  - <span data-ttu-id="79ebe-134">Передает данные в присоединенный отладчик.</span><span class="sxs-lookup"><span data-stu-id="79ebe-134">Writes to an attached debugger.</span></span>
  - <span data-ttu-id="79ebe-135">В системах `*nix` ведет запись в stderr, если задан параметр `COMPlus_DebugWriteToStdErr`.</span><span class="sxs-lookup"><span data-stu-id="79ebe-135">On `*nix` writes to stderr if `COMPlus_DebugWriteToStdErr` is set.</span></span>
  - <span data-ttu-id="79ebe-136">Используйте этот API при создании журналов, которые будут включены только в сборках отладки.</span><span class="sxs-lookup"><span data-stu-id="79ebe-136">Use this API when creating logs that will be enabled only in debug builds.</span></span>

### <a name="logging-events"></a><span data-ttu-id="79ebe-137">События ведения журнала</span><span class="sxs-lookup"><span data-stu-id="79ebe-137">Logging events</span></span>

<span data-ttu-id="79ebe-138">Следующие API-интерфейсы больше ориентированы на события.</span><span class="sxs-lookup"><span data-stu-id="79ebe-138">The following APIs are more event oriented.</span></span> <span data-ttu-id="79ebe-139">Они сохраняют в журнал не простые строки текста, а целые объекты событий.</span><span class="sxs-lookup"><span data-stu-id="79ebe-139">Rather than logging simple strings they log event objects.</span></span>

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-140">EventSource является основным корневым API для трассировки в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="79ebe-140">EventSource is the primary root .NET Core tracing API.</span></span>
  - <span data-ttu-id="79ebe-141">Доступен во всех стандартных версиях .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="79ebe-141">Available in all .NET Standard versions.</span></span>
  - <span data-ttu-id="79ebe-142">Поддерживает трассировку только сериализуемых объектов.</span><span class="sxs-lookup"><span data-stu-id="79ebe-142">Only allows tracing serializable objects.</span></span>
  - <span data-ttu-id="79ebe-143">Сохраняет данные в подключенные [прослушиватели событий](xref:System.Diagnostics.Tracing.EventListener).</span><span class="sxs-lookup"><span data-stu-id="79ebe-143">Writes to the attached [event listeners](xref:System.Diagnostics.Tracing.EventListener).</span></span>
  - <span data-ttu-id="79ebe-144">.NET Core предоставляет следующие прослушиватели:</span><span class="sxs-lookup"><span data-stu-id="79ebe-144">.NET Core provides listeners for:</span></span>
    - <span data-ttu-id="79ebe-145">EventPipe из .NET Core на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="79ebe-145">.NET Core's EventPipe on all platforms</span></span>
    - [<span data-ttu-id="79ebe-146">Трассировка событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="79ebe-146">Event Tracing for Windows (ETW)</span></span>](/windows/win32/etw/event-tracing-portal)
    - [<span data-ttu-id="79ebe-147">Платформа трассировки LTTng для Linux.</span><span class="sxs-lookup"><span data-stu-id="79ebe-147">LTTng tracing framework for Linux</span></span>](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-148">Предоставляется в составе .NET Core и в отдельном [пакете NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79ebe-148">Included in .NET Core and as a [NuGet package](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) for .NET Framework.</span></span>
  - <span data-ttu-id="79ebe-149">Позволяет выполнять внутрипроцессную трассировку для несериализуемых объектов.</span><span class="sxs-lookup"><span data-stu-id="79ebe-149">Allows in-process tracing of non-serializable objects.</span></span>
  - <span data-ttu-id="79ebe-150">Содержит мост, который поддерживает сохранение выбранных полей регистрируемых объектов в <xref:System.Diagnostics.Tracing.EventSource>.</span><span class="sxs-lookup"><span data-stu-id="79ebe-150">Includes a bridge to allow selected fields of logged objects to be written to an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-151">Предоставляет однозначный метод идентификации сообщений журнала, создаваемых по определенному действию или транзакции.</span><span class="sxs-lookup"><span data-stu-id="79ebe-151">Provides a definitive way to identify log messages resulting from a specific activity or transaction.</span></span> <span data-ttu-id="79ebe-152">Этот объект можно использовать для согласования журналов из нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="79ebe-152">This object can be used to correlate logs across different services.</span></span>

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - <span data-ttu-id="79ebe-153">Только для Windows.</span><span class="sxs-lookup"><span data-stu-id="79ebe-153">Windows only.</span></span>
  - <span data-ttu-id="79ebe-154">Сохраняет сообщения в журнал событий Windows.</span><span class="sxs-lookup"><span data-stu-id="79ebe-154">Writes messages to the Windows Event Log.</span></span>
  - <span data-ttu-id="79ebe-155">Системные администраторы ожидают, что сообщения об ошибках, приводящих к сбоям приложений, будут отображаться в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="79ebe-155">System administrators expect fatal application error messages to appear in the Windows Event Log.</span></span>

## <a name="ilogger-and-logging-frameworks"></a><span data-ttu-id="79ebe-156">ILogger и платформы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="79ebe-156">ILogger and logging frameworks</span></span>

<span data-ttu-id="79ebe-157">Низкоуровневые API могут оказаться плохим вариантом для некоторых задач ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="79ebe-157">The low-level APIs may not be the right choice for your logging needs.</span></span> <span data-ttu-id="79ebe-158">Возможно, вам лучше подойдет платформа ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="79ebe-158">You may want to consider a logging framework.</span></span>

<span data-ttu-id="79ebe-159">На основе интерфейса <xref:Microsoft.Extensions.Logging.ILogger> был создан единый интерфейс ведения журналов, который позволяет добавлять средства ведения журнала через внедрение зависимостей.</span><span class="sxs-lookup"><span data-stu-id="79ebe-159">The <xref:Microsoft.Extensions.Logging.ILogger> interface has been used to create a common logging interface where the loggers can be inserted through dependency injection.</span></span>

<span data-ttu-id="79ebe-160">Например, .NET предоставляет поддержку большого числа встроенных и сторонних платформ, что позволяет вам правильно выбрать нужный вариант для своего приложения:</span><span class="sxs-lookup"><span data-stu-id="79ebe-160">For instance, to allow you to make the best choice for your application .NET offers support for a selection of built-in and third-party frameworks:</span></span>

- [<span data-ttu-id="79ebe-161">Встроенные поставщики ведения журналов .NET</span><span class="sxs-lookup"><span data-stu-id="79ebe-161">.NET Built-in logging providers</span></span>](../extensions/logging-providers.md#built-in-logging-providers)
- [<span data-ttu-id="79ebe-162">Сторонние поставщики ведения журналов для .NET</span><span class="sxs-lookup"><span data-stu-id="79ebe-162">.NET Third-party logging providers</span></span>](../extensions/logging-providers.md#third-party-logging-providers)

## <a name="logging-related-references"></a><span data-ttu-id="79ebe-163">Справочные материалы по ведению журналов</span><span class="sxs-lookup"><span data-stu-id="79ebe-163">Logging related references</span></span>

- [<span data-ttu-id="79ebe-164">Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug</span><span class="sxs-lookup"><span data-stu-id="79ebe-164">How to: Compile Conditionally with Trace and Debug</span></span>](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [<span data-ttu-id="79ebe-165">Практическое руководство. Добавление операторов трассировки в код приложения</span><span class="sxs-lookup"><span data-stu-id="79ebe-165">How to: Add Trace Statements to Application Code</span></span>](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- <span data-ttu-id="79ebe-166">Статья [о ведении журналов в .NET](../extensions/logging.md) содержит обзор поддерживаемых технологий ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="79ebe-166">[Logging in .NET](../extensions/logging.md) provides an overview of the logging techniques it supports.</span></span>

- <span data-ttu-id="79ebe-167">[Интерполяция строк в C#](../../csharp/language-reference/tokens/interpolated.md) помогает упростить создание кода для ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="79ebe-167">[C# string interpolation](../../csharp/language-reference/tokens/interpolated.md) can simplify writing logging code.</span></span>

- <span data-ttu-id="79ebe-168">Свойство <xref:System.Exception.Message?displayProperty=nameWithType> очень полезно для ведения журналов исключений.</span><span class="sxs-lookup"><span data-stu-id="79ebe-168">The <xref:System.Exception.Message?displayProperty=nameWithType> property is useful for logging exceptions.</span></span>

- <span data-ttu-id="79ebe-169">Класс <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> позволяет передать в журнал сведения о текущем состоянии стека.</span><span class="sxs-lookup"><span data-stu-id="79ebe-169">The <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> class can be useful to provide stack info in your logs.</span></span>

## <a name="performance-considerations"></a><span data-ttu-id="79ebe-170">Вопросы производительности</span><span class="sxs-lookup"><span data-stu-id="79ebe-170">Performance considerations</span></span>

<span data-ttu-id="79ebe-171">Форматирование строк может создавать значительную нагрузку на ЦП.</span><span class="sxs-lookup"><span data-stu-id="79ebe-171">String formatting can take noticeable CPU processing time.</span></span>

<span data-ttu-id="79ebe-172">В приложениях, для которых производительность критически важна, мы рекомендуем соблюдать следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="79ebe-172">In performance critical applications, it's recommended that you:</span></span>

- <span data-ttu-id="79ebe-173">Не создавайте большой объем журналов, если их никто не проверяет.</span><span class="sxs-lookup"><span data-stu-id="79ebe-173">Avoid lots of logging when no one is listening.</span></span> <span data-ttu-id="79ebe-174">Не создавайте ресурсоемкие сообщения журнала, не проверив сначала, включено ли ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="79ebe-174">Avoid constructing costly logging messages by checking if logging is enabled first.</span></span>
- <span data-ttu-id="79ebe-175">Включайте в журнал только полезные сведения.</span><span class="sxs-lookup"><span data-stu-id="79ebe-175">Only log what's useful.</span></span>
- <span data-ttu-id="79ebe-176">Красивое форматирование отложите на этап анализа данных.</span><span class="sxs-lookup"><span data-stu-id="79ebe-176">Defer fancy formatting to the analysis stage.</span></span>
