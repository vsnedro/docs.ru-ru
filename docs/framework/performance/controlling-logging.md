---
title: Контроль ведения журнала .NET Framework
description: Используйте средство трассировки событий для Windows (ETW) для управления ведением журнала .NET и записи событий среды CLR. Используйте такие средства, как logman, Tracerpt и XPerf.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: bce5ea41149dc3b19106031fae202872dd8a8fb5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553809"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="77aa4-104">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="77aa4-104">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="77aa4-105">Трассировку событий для Windows (ETW) можно использовать для записи событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="77aa4-105">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="77aa4-106">Для создания и просмотра трассировки можно использовать следующие инструменты.</span><span class="sxs-lookup"><span data-stu-id="77aa4-106">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="77aa4-107">Программы командной строки [Logman](/windows-server/administration/windows-commands/logman) и [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), входящие в состав операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="77aa4-107">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="77aa4-108">Программы [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) в составе [набора средств для оценки производительности Windows](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="77aa4-108">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="77aa4-109">Дополнительные сведения о программе Xperf см. в [блоге, посвященном производительности Windows](/archive/blogs/pigscanfly/).</span><span class="sxs-lookup"><span data-stu-id="77aa4-109">For more information about Xperf, see the [Windows Performance blog](/archive/blogs/pigscanfly/).</span></span>

<span data-ttu-id="77aa4-110">Для регистрации событий среды CLR на компьютере должен быть установлен поставщик среды CLR.</span><span class="sxs-lookup"><span data-stu-id="77aa4-110">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="77aa4-111">Чтобы проверить, установлен ли этот поставщик, введите в командной строке `logman query providers`.</span><span class="sxs-lookup"><span data-stu-id="77aa4-111">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="77aa4-112">Откроется список поставщиков.</span><span class="sxs-lookup"><span data-stu-id="77aa4-112">A list of providers is displayed.</span></span> <span data-ttu-id="77aa4-113">В этом списке должна находиться следующая запись для поставщика среды CLR.</span><span class="sxs-lookup"><span data-stu-id="77aa4-113">This list should contain an entry for the CLR provider, as follows.</span></span>

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="77aa4-114">Если поставщик среды CLR не указан, его можно установить в Windows Vista и операционных системах более поздних версий с помощью программы командной строки Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil).</span><span class="sxs-lookup"><span data-stu-id="77aa4-114">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="77aa4-115">Откройте окно командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="77aa4-115">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="77aa4-116">Измените каталог подсказки на папку .NET Framework 4 (%WINDIR%\Microsoft.NET\Framework [64] \v4. \<.NET version> \ ).</span><span class="sxs-lookup"><span data-stu-id="77aa4-116">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="77aa4-117">Эта папка содержит файл CLR-ETW.man.</span><span class="sxs-lookup"><span data-stu-id="77aa4-117">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="77aa4-118">Чтобы установить поставщик среды CLR, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="77aa4-118">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="77aa4-119">Регистрация событий ETW в среде CLR</span><span class="sxs-lookup"><span data-stu-id="77aa4-119">Capturing CLR ETW Events</span></span>

<span data-ttu-id="77aa4-120">Программы командной строки [Logman](/windows-server/administration/windows-commands/logman) и [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) можно использовать для захвата событий трассировки событий Windows, а программы [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) и [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) — для расшифровки событий трассировки.</span><span class="sxs-lookup"><span data-stu-id="77aa4-120">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="77aa4-121">Чтобы включить ведение журнала, пользователь должен указать следующее.</span><span class="sxs-lookup"><span data-stu-id="77aa4-121">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="77aa4-122">Поставщика, с которым следует обмениваться информацией.</span><span class="sxs-lookup"><span data-stu-id="77aa4-122">The provider to communicate to.</span></span>

- <span data-ttu-id="77aa4-123">64-разрядное число, представляющее набор ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="77aa4-123">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="77aa4-124">Каждое ключевое слово представляет набор событий, которые может включить поставщик.</span><span class="sxs-lookup"><span data-stu-id="77aa4-124">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="77aa4-125">Число представляет комбинированный набор ключевых слов, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="77aa4-125">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="77aa4-126">Небольшое число, представляющее уровень (детализации) ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="77aa4-126">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="77aa4-127">Уровень 1 является наименее детальным, а уровень 5 — наиболее детальным.</span><span class="sxs-lookup"><span data-stu-id="77aa4-127">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="77aa4-128">Уровень 0 является значением по умолчанию, его назначение зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="77aa4-128">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="77aa4-129">Регистрация событий ETW среды CLR с помощью программы Logman</span><span class="sxs-lookup"><span data-stu-id="77aa4-129">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="77aa4-130">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-130">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="77aa4-131">где:</span><span class="sxs-lookup"><span data-stu-id="77aa4-131">where:</span></span>

    - <span data-ttu-id="77aa4-132">Параметр `-p` задает GUID поставщика.</span><span class="sxs-lookup"><span data-stu-id="77aa4-132">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="77aa4-133">`0x1CCBD` задает категории создаваемых событий.</span><span class="sxs-lookup"><span data-stu-id="77aa4-133">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="77aa4-134">`0x5` задает уровень регистрации (в данном случае подробный (5)).</span><span class="sxs-lookup"><span data-stu-id="77aa4-134">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="77aa4-135">Параметр `-ets` указывает программе Logman отправлять команды сеансам трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="77aa4-135">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="77aa4-136">Параметр `-ct perf`, определяет, что для записи отметки времени каждого события будет использоваться функция `QueryPerformanceCounter`.</span><span class="sxs-lookup"><span data-stu-id="77aa4-136">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="77aa4-137">Чтобы остановить регистрацию событий, введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-137">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="77aa4-138">Эта команда создает двоичный файл трассировки clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="77aa4-138">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="77aa4-139">Регистрация событий ETW среды CLR с помощью программы Xperf</span><span class="sxs-lookup"><span data-stu-id="77aa4-139">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="77aa4-140">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-140">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="77aa4-141">где GUID — это GUID поставщика ETW среды CLR, а `0x1CCBD:5` выполняет трассировку всех событий на уровне 5 (детальный) и ниже.</span><span class="sxs-lookup"><span data-stu-id="77aa4-141">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="77aa4-142">Чтобы остановить трассировку, введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-142">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="77aa4-143">Эта команда создает файл трассировки clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="77aa4-143">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="77aa4-144">Просмотр событий ETW среды CLR</span><span class="sxs-lookup"><span data-stu-id="77aa4-144">Viewing CLR ETW Events</span></span>

<span data-ttu-id="77aa4-145">Перечисленные ниже команды используются для просмотра событий ETW среды CLR.</span><span class="sxs-lookup"><span data-stu-id="77aa4-145">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="77aa4-146">Описание событий см. в разделе [События трассировки событий Windows в среде CLR](clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="77aa4-146">For a description of the events, see [CLR ETW Events](clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="77aa4-147">Просмотр событий ETW среды CLR с помощью программы Tracerpt</span><span class="sxs-lookup"><span data-stu-id="77aa4-147">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="77aa4-148">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-148">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="77aa4-149">Эта команда создает два файла: dumpfile.xml и summary.txt.</span><span class="sxs-lookup"><span data-stu-id="77aa4-149">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="77aa4-150">Файл dumpfile.xml содержит список всех событий, а файл summary.txt содержит сводку событий.</span><span class="sxs-lookup"><span data-stu-id="77aa4-150">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="77aa4-151">Просмотр событий ETW среды CLR с помощью программы Xperf</span><span class="sxs-lookup"><span data-stu-id="77aa4-151">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="77aa4-152">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-152">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="77aa4-153">Эта команда открывает программу Xperf просмотра ETL-файлов.</span><span class="sxs-lookup"><span data-stu-id="77aa4-153">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="77aa4-154">В этом средстве просмотра события CLR показаны в представлении **Универсальные события**.</span><span class="sxs-lookup"><span data-stu-id="77aa4-154">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="77aa4-155">Чтобы отобразить таблицу данных событий, распределенных по типу, в этом представлении выберите часовой пояс, щелкните правой кнопкой мыши и выберите **Сводка**.</span><span class="sxs-lookup"><span data-stu-id="77aa4-155">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="77aa4-156">Преобразование ETL-файла в файл данных с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="77aa4-156">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="77aa4-157">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="77aa4-157">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="77aa4-158">Эта команда XPerf помещает события в дамп в виде файла с разделителями-запятыми (CSV-файл), который впоследствии можно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="77aa4-158">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="77aa4-159">Поскольку у разных событий поля разные, этот CSV-файл содержит несколько строк заголовков, расположенных перед данными.</span><span class="sxs-lookup"><span data-stu-id="77aa4-159">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="77aa4-160">Первое поле каждой строки является типом события с указанием заголовка, который должен использоваться для определения остальных полей.</span><span class="sxs-lookup"><span data-stu-id="77aa4-160">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="77aa4-161">См. также</span><span class="sxs-lookup"><span data-stu-id="77aa4-161">See also</span></span>

- [<span data-ttu-id="77aa4-162">Набор средств для оценки производительности Windows</span><span class="sxs-lookup"><span data-stu-id="77aa4-162">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="77aa4-163">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="77aa4-163">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
