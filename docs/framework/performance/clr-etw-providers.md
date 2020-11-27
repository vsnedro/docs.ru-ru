---
title: Поставщики ETW среды CLR
description: 'Ознакомьтесь со сведениями о двух поставщиках трассировки событий среды CLR для Windows (ETW): поставщик рунтимне и поставщик очистки.'
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, CLR providers
- CLR ETW providers
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
ms.openlocfilehash: f537a2e0557f1b0434d1f303d74f9cd48f157edc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283878"
---
# <a name="clr-etw-providers"></a><span data-ttu-id="3a9d2-103">Поставщики ETW среды CLR</span><span class="sxs-lookup"><span data-stu-id="3a9d2-103">CLR ETW Providers</span></span>

<span data-ttu-id="3a9d2-104">В общеязыковой среде выполнения (CLR) представлены два поставщика: поставщик среды выполнения и поставщик очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-104">The common language runtime (CLR) has two providers: the runtime provider and the rundown provider.</span></span>  
  
 <span data-ttu-id="3a9d2-105">Поставщик среды выполнения вызывает события в зависимости от того, какие ключевые слова (категории событий) активированы.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-105">The runtime provider raises events, depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="3a9d2-106">Например, с помощью ключевого слова `LoaderKeyword` можно активировать сбор событий загрузчика.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-106">For example, you can collect loader events by enabling the `LoaderKeyword` keyword.</span></span>  
  
 <span data-ttu-id="3a9d2-107">События трассировки событий Windows регистрируются в файле с расширением ETL, которое впоследствии может быть обработано при необходимости в файлах значений с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="3a9d2-107">Event Tracing for Windows (ETW) events are logged into a file that has an .etl extension, which can later be post-processed in comma-separated value (.csv) files as needed.</span></span> <span data-ttu-id="3a9d2-108">Дополнительные сведения о преобразовании ETL-файлов в файлы с расширением CSV см. в разделе [Контроль ведения журнала .NET Framework](controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="3a9d2-108">For information about how to convert the .etl file to a .csv file, see [Controlling .NET Framework Logging](controlling-logging.md).</span></span>  
  
## <a name="the-runtime-provider"></a><span data-ttu-id="3a9d2-109">Поставщик среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3a9d2-109">The Runtime Provider</span></span>  

 <span data-ttu-id="3a9d2-110">Поставщик среды выполнения является основным поставщиком трассировки событий Windows в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-110">The runtime provider is the main CLR ETW provider.</span></span>  
  
 <span data-ttu-id="3a9d2-111">Поставщик среды выполнения CLR имеет GUID e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-111">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
 <span data-ttu-id="3a9d2-112">Примеры записи в журнал и просмотра событий трассировки событий Windows в среде CLR с использованием общедоступных средств см. в разделе [Контроль ведения журнала .NET Framework](controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="3a9d2-112">For examples of how to log and view CLR ETW events by using commonly available tools, see [Controlling .NET Framework Logging](controlling-logging.md).</span></span>  
  
 <span data-ttu-id="3a9d2-113">Помимо таких ключевых слов, как `LoaderKeyword`, вам может потребоваться включить ключевые слова для ведения журнала событий, которые могут возникать слишком часто.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-113">In addition to using keywords such as `LoaderKeyword`, you may have to enable keywords for logging events that may be raised too frequently.</span></span> <span data-ttu-id="3a9d2-114">Такие события активируются с помощью ключевых слов `StartEnumerationKeyword` и `EndEnumerationKeyword`, описание которых приводится в разделе [Ключевые слова и уровни среды CLR (трассировка событий Windows)](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3a9d2-114">The `StartEnumerationKeyword` and the `EndEnumerationKeyword` keywords enable these events and are summarized in [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>  
  
## <a name="the-rundown-provider"></a><span data-ttu-id="3a9d2-115">Поставщик очистки</span><span class="sxs-lookup"><span data-stu-id="3a9d2-115">The Rundown Provider</span></span>  

 <span data-ttu-id="3a9d2-116">В некоторых особых ситуациях необходимо активировать поставщик очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-116">The rundown provider must be turned on for certain special-purpose uses.</span></span> <span data-ttu-id="3a9d2-117">Тем не менее в большинстве случаев достаточно использовать поставщик среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-117">However, for a majority of users, the runtime provider should suffice.</span></span>  
  
 <span data-ttu-id="3a9d2-118">Поставщик очистки среды CLR имеет GUID A669021C-C450-4609-A035-5AF59AF4DF18.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-118">The CLR rundown provider GUID is A669021C-C450-4609-A035-5AF59AF4DF18.</span></span>  
  
 <span data-ttu-id="3a9d2-119">Как правило, ведение журнала трассировки событий Windows активируется до запуска процесса и отключается после выхода из него.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-119">Normally, ETW logging is enabled before a process launches, and the logging is turned off after the process exits.</span></span> <span data-ttu-id="3a9d2-120">Тем не менее, если включить трассировку событий Windows во время выполнения процесса, потребуется дополнительная информация о процессе.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-120">However, if ETW logging is turned on while the process is executing, additional information is needed about the process.</span></span> <span data-ttu-id="3a9d2-121">Например, для разрешения символов требуется вести журнал событий для методов, которые были уже загружены до того, как было включено ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-121">For example, for symbol resolution you have to log method events for methods that were already loaded before logging was turned on.</span></span>  
  
 <span data-ttu-id="3a9d2-122">События `DCStart` и `DCEnd` захватывают состояние процесса на момент запуска и остановки сбора данных.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-122">The `DCStart` and `DCEnd` events capture the state of the process when data collection was started and stopped.</span></span> <span data-ttu-id="3a9d2-123">(Состояние относится к информации на высоком уровне, включая методы, которые уже были скомпилированы JIT-компилятором и загруженные сборки.) Эти два события могут предоставить сведения о том, что уже произошло в процессе. Например, методы, скомпилированные с помощью JIT-компилятора, и т. д.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-123">(State refers to information at a high level, including the methods that were already just-in-time (JIT) compiled and assemblies that were loaded.) These two events can provide information about what has already happened in the process; for example, which methods were JIT- compiled, and so on.</span></span>  
  
 <span data-ttu-id="3a9d2-124">При использовании поставщика очистки возникают только события, в именах которых содержатся строки `DC`, `DCStart`, `DCEnd` или `DCInit`.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-124">Only the events with `DC`, `DCStart`, `DCEnd`, or `DCInit` in their names are raised under the rundown provider.</span></span> <span data-ttu-id="3a9d2-125">Кроме того, эти события создаются только при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-125">Additionally, these events are raised only under the rundown provider.</span></span>  
  
 <span data-ttu-id="3a9d2-126">В дополнение к фильтрам ключевых слов событий поставщик очистки также поддерживает ключевые слова `StartRundownKeyword` и `EndRundownKeyword`, обеспечивающие целевую фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-126">In addition to the event keyword filters, the rundown provider also supports the `StartRundownKeyword` and `EndRundownKeyword` keywords to provide targeted filtering.</span></span>  
  
### <a name="start-rundown"></a><span data-ttu-id="3a9d2-127">Начальная очистка</span><span class="sxs-lookup"><span data-stu-id="3a9d2-127">Start Rundown</span></span>  

 <span data-ttu-id="3a9d2-128">Начальная очистка инициируется в тот момент, когда с помощью ключевого слова `StartRundownKeyword` активируется ведение журнала для поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-128">A start rundown is triggered when logging under the rundown provider is enabled with the `StartRundownKeyword` keyword.</span></span> <span data-ttu-id="3a9d2-129">В результате этого возникает событие `DCStart`, в котором фиксируется состояние системы.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-129">This causes the `DCStart` event to be raised, and captures the state of the system.</span></span> <span data-ttu-id="3a9d2-130">Перед началом перечисления возникает событие `DCStartInit`.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-130">Before the start of the enumeration, the `DCStartInit` event is raised.</span></span> <span data-ttu-id="3a9d2-131">По окончании перечисления возникает событие `DCStartComplete`, которое уведомляет контроллер о нормальном завершении сбора данных.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-131">At the end of the enumeration, the `DCStartComplete` event is raised to notify the controller that data collection terminated normally.</span></span>  
  
### <a name="end-rundown"></a><span data-ttu-id="3a9d2-132">Завершающая очистка</span><span class="sxs-lookup"><span data-stu-id="3a9d2-132">End Rundown</span></span>  

 <span data-ttu-id="3a9d2-133">Завершающая очистка инициируется в тот момент, когда с помощью ключевого слова `EndRundownKeyword` отключается ведение журнала для поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-133">An end rundown is triggered when logging under the rundown provider is enabled with the `EndRundownKeyword` keyword.</span></span> <span data-ttu-id="3a9d2-134">Завершающая очистка прекращает профилирование для процесса, выполнение которого продолжается.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-134">End rundown stops profiling on a process that continues to execute.</span></span> <span data-ttu-id="3a9d2-135">События `DCEnd` фиксируют состояние системы в момент остановки профилирования.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-135">The `DCEnd` events capture the state of the system when profiling is stopped.</span></span>  
  
 <span data-ttu-id="3a9d2-136">Перед началом перечисления возникает событие `DCEndInit`.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-136">Before the start of the enumeration, the `DCEndInit` event is raised.</span></span> <span data-ttu-id="3a9d2-137">По окончании перечисления возникает событие `DCEndComplete`, которое уведомляет потребителя о нормальном завершении сбора данных.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-137">At the end of the enumeration, the `DCEndComplete` event is raised to notify the consumer that data collection terminated normally.</span></span> <span data-ttu-id="3a9d2-138">Начальная и завершающая очистка используются преимущественно для управляемого разрешения символов.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-138">Start rundown and end rundown are primarily used for managed symbol resolution.</span></span> <span data-ttu-id="3a9d2-139">Начальная очистка может предоставить сведения о диапазоне адресов для методов, которые уже прошли JIT-компиляцию до начала сеанса профилирования.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-139">Start rundown can provide address range information for methods that were already JIT-compiled before the profiling session was started.</span></span> <span data-ttu-id="3a9d2-140">Завершающая очистка может предоставить сведения о диапазоне адресов для всех методов, которые уже прошли JIT-компиляцию непосредственно перед отключением профилирования.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-140">End rundown can provide address range information for all methods that have been JIT-compiled when profiling is about to be turned off.</span></span>  
  
 <span data-ttu-id="3a9d2-141">Завершающая очистка не выполняется автоматически, если сеанс профилирования остановлен.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-141">End rundown does not happen automatically when a profiling session is stopped.</span></span> <span data-ttu-id="3a9d2-142">Вместо этого средство, которое пытается выполнить управляемое разрешение символов, должно явно вызывать сеанс поставщика среды выполнения CLR с включенным ключевым словом `EndRundownKeyword` непосредственно перед остановкой профилирования.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-142">Instead, a tool that is seeking to perform managed symbol resolution has to explicitly invoke a CLR rundown provider session with the `EndRundownKeyword` keyword enabled, just before profiling is stopped.</span></span>  
  
 <span data-ttu-id="3a9d2-143">Несмотря на то, что в ходе начальной и завершающей очистки методу могут предоставляться сведения о диапазоне адресов для управляемого разрешения символов, мы рекомендуем использовать ключевое слово `EndRundownKeyword` (предоставляет события `DCEnd`) вместо ключевого слова `StartRundownKeyword` (предоставляет события `DCStart`).</span><span class="sxs-lookup"><span data-stu-id="3a9d2-143">Although either start rundown or end rundown can provide method address range information for managed symbol resolution, we recommend that you use the `EndRundownKeyword` keyword (which supplies `DCEnd` events) instead of the `StartRundownKeyword` keyword (which supplies `DCStart` events).</span></span> <span data-ttu-id="3a9d2-144">Это связано с тем, что ключевое слово `StartRundownKeyword` запускает очистку во время сеанса профилирования, что может помешать выполнению профилируемого сценария.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-144">Using `StartRundownKeyword` causes the rundown to happen during the profiling session, which may disturb the profiled scenario.</span></span>  
  
## <a name="etw-data-collection-using-runtime-and-rundown-providers"></a><span data-ttu-id="3a9d2-145">Сбор данных трассировки событий Windows с помощью поставщиков среды выполнения и очистки</span><span class="sxs-lookup"><span data-stu-id="3a9d2-145">ETW Data Collection Using Runtime and Rundown Providers</span></span>  

 <span data-ttu-id="3a9d2-146">В следующем примере демонстрируется, как использовать поставщик очистки среды CLR, чтобы обеспечить разрешение символов для управляемых процессов с минимальными последствиями независимо от того, начинаются или завершаются процессы во время профилирования или за пределами этого периода.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-146">The following example demonstrates how to use the CLR rundown provider in a way that allows symbol resolution of managed processes with minimal impact, regardless of whether the processes start or end inside or outside the profiled window.</span></span>  
  
1. <span data-ttu-id="3a9d2-147">Включение ведения журнала трассировки событий Windows с использованием поставщика среды выполнения CLR:</span><span class="sxs-lookup"><span data-stu-id="3a9d2-147">Turn on ETW logging by using the CLR runtime provider:</span></span>  
  
    ```console
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl
    ```  
  
     <span data-ttu-id="3a9d2-148">Журнал будет сохраняться в файле clr1.etl.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-148">The log will be saved to the clr1.etl file.</span></span>  
  
2. <span data-ttu-id="3a9d2-149">Чтобы остановить профилирование во время выполнения процесса, запустите поставщик очистки для захвата событий `DCEnd`:</span><span class="sxs-lookup"><span data-stu-id="3a9d2-149">To stop profiling while the process continues to execute, start the rundown provider to capture the `DCEnd` events:</span></span>  
  
    ```console
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl
    ```  
  
     <span data-ttu-id="3a9d2-150">В результате включается сбор событий `DCEnd` для начала сеанса очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-150">This enables the collection of `DCEnd` events to start a rundown session.</span></span> <span data-ttu-id="3a9d2-151">Сбор всех событий может занимать от 30 до 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-151">You may need to wait 30 to 60 seconds for all events to be collected.</span></span> <span data-ttu-id="3a9d2-152">Журнал будет сохраняться в файле clr1.et2.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-152">The log will be saved to the clr1.et2 file.</span></span>  
  
3. <span data-ttu-id="3a9d2-153">Отключение профилирования трассировки всех событий Windows:</span><span class="sxs-lookup"><span data-stu-id="3a9d2-153">Turn off all ETW profiling:</span></span>  
  
    ```console
    xperf -stop clrRundown
    xperf -stop clr  
    ```  
  
4. <span data-ttu-id="3a9d2-154">Объединение профилей в один файл журнала:</span><span class="sxs-lookup"><span data-stu-id="3a9d2-154">Merge the profiles to create one log file:</span></span>  
  
    ```console
    xperf -merge clr1.etl clr2.etl merged.etl  
    ```  
  
     <span data-ttu-id="3a9d2-155">В объединенном ETL-файле будут содержаться события из сеансов поставщиков среды выполнения и очистки.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-155">The merged.etl file will contain the events from the runtime and the rundown provider sessions.</span></span>  
  
 <span data-ttu-id="3a9d2-156">Если пользователь запрашивает остановку профилирования, средство может выполнять шаги 2 и 3 (запуск сеанса очистки и завершение профилирования) вместо немедленного отключения профилирования.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-156">A tool can execute steps 2 and 3 (starting a rundown session and then terminating profiling) instead of immediately turning off profiling when a user requests profiling to be stopped.</span></span> <span data-ttu-id="3a9d2-157">Кроме того, это средство может выполнить шаг 4.</span><span class="sxs-lookup"><span data-stu-id="3a9d2-157">A tool can also execute step 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9d2-158">См. также</span><span class="sxs-lookup"><span data-stu-id="3a9d2-158">See also</span></span>

- [<span data-ttu-id="3a9d2-159">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="3a9d2-159">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
