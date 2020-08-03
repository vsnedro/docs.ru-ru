---
title: Fuslogvw.exe (средство просмотра журнала привязки сборок)
description: Используйте Fuslogvw.exe, средство просмотра журнала привязки сборок. Это средство выводит подробные сведения о привязке сборок, помогающие определить причину, по которой .NET не находит сборку во время выполнения.
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: 949f9cf98d5eb4e100be9837be120038f085cc40
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167124"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="e5f2f-104">Fuslogvw.exe (средство просмотра журнала привязки сборок)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-104">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>

<span data-ttu-id="e5f2f-105">Средство просмотра журнала привязки сборок выводит подробные сведения об ошибках привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-105">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="e5f2f-106">Эта информация поможет определить причину, по которой .NET Framework не находит сборку во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-106">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="e5f2f-107">Ошибки обычно вызваны развертыванием сборки в неверном расположении, использованием машинного образа, который более не является допустимым, а также несовпадением версий или языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-107">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="e5f2f-108">Если среде CLR не удается найти сборку, обычно в приложении отображается исключение <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-108">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5f2f-109">Средство просмотра Fuslogvw.exe необходимо запускать с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-109">You must run fuslogvw.exe with administrator privileges.</span></span>

<span data-ttu-id="e5f2f-110">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="e5f2f-111">Запускайте его из командной строки разработчика для Visual Studio (или командной строки в Windows 7), используя учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7) with administrator credentials.</span></span> <span data-ttu-id="e5f2f-112">Дополнительные сведения см. в разделе [Командные строки](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-112">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="e5f2f-113">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-113">At the command prompt, type the following:</span></span>

```console
fuslogvw
```

<span data-ttu-id="e5f2f-114">В средстве просмотра отображаются записи всех ошибок привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-114">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="e5f2f-115">Для каждой ошибки указывается: приложение, выполнявшее привязку; сборка, для которой выполнялась привязка, включая имя, версию, культуру и открытый ключ; дата и время ошибки.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-115">For each failure, the viewer describes the application that initiated the bind; the assembly the bind is for, including name, version, culture and public key; and the date and time of the failure.</span></span>

### <a name="to-change-the-log-location-view"></a><span data-ttu-id="e5f2f-116">Изменение представления расположения журнала</span><span class="sxs-lookup"><span data-stu-id="e5f2f-116">To change the log location view</span></span>

1. <span data-ttu-id="e5f2f-117">Чтобы просмотреть ошибки привязки для всех типов приложений, выберите параметр **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-117">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="e5f2f-118">Записи журнала по умолчанию хранятся в каталогах для отдельных пользователей на жестком диске в кэше WinINet.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-118">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>

2. <span data-ttu-id="e5f2f-119">Чтобы просмотреть ошибки привязки в пользовательском каталоге, выберите параметр **Настраиваемый**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-119">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="e5f2f-120">Необходимо указать расположение, в котором среда выполнения будет размещать журналы. Для этого задайте имя каталога в диалоговом окне **Параметры журнала**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-120">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="e5f2f-121">Каталог должен быть пустым и содержать только создаваемые средой выполнения файлы.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-121">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="e5f2f-122">Если в этом каталоге находится исполняемый файл и он создает ошибку, которую требуется занести в журнал, ошибка не будет зарегистрирована, так как средство просмотра попытается создать каталог с именем исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-122">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="e5f2f-123">Кроме того, попытка запустить исполняемый файл из местоположения журнала завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-123">In addition, an attempt to run an executable from the log location will fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5f2f-124">Рекомендуется использовать расположение привязки по умолчанию, а не настраиваемое расположение.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-124">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="e5f2f-125">Среда выполнения хранит расположение привязки, используемое по умолчанию, в кэше WinINet и потому автоматически очищает его. Настраиваемое расположение привязки необходимо очищать вручную.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-125">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>

### <a name="to-view-details-about-a-specific-failure"></a><span data-ttu-id="e5f2f-126">Просмотр сведений о конкретной ошибке</span><span class="sxs-lookup"><span data-stu-id="e5f2f-126">To view details about a specific failure</span></span>

1. <span data-ttu-id="e5f2f-127">Выберите имя приложения нужной записи в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-127">Select the application name of the desired entry in the viewer.</span></span>

2. <span data-ttu-id="e5f2f-128">Нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-128">Click the **View Log** button.</span></span> <span data-ttu-id="e5f2f-129">Также можно дважды щелкнуть выбранную запись.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-129">Alternately, you can double-click the selected entry.</span></span>

    <span data-ttu-id="e5f2f-130">Средство отобразит следующие сведения о выбранной ошибке привязки:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-130">The tool displays the following details about the selected bind failure:</span></span>

    - <span data-ttu-id="e5f2f-131">причина возникновения ошибки, например "файл не найден" или "несоответствие версий";</span><span class="sxs-lookup"><span data-stu-id="e5f2f-131">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>

    - <span data-ttu-id="e5f2f-132">сведения о приложении, выполнявшем привязку, в том числе имя, корневой каталог приложения (AppBase) и описание закрытого пути поиска при его наличии;</span><span class="sxs-lookup"><span data-stu-id="e5f2f-132">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>

    - <span data-ttu-id="e5f2f-133">идентификатор сборки, которую ищет средство;</span><span class="sxs-lookup"><span data-stu-id="e5f2f-133">The identity of the assembly the tool is looking for.</span></span>

    - <span data-ttu-id="e5f2f-134">описание любых примененных политик версий приложения, издателя и администратора;</span><span class="sxs-lookup"><span data-stu-id="e5f2f-134">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>

    - <span data-ttu-id="e5f2f-135">сведения о том, была ли обнаружена сборка в [глобальном кэше сборок](../app-domains/gac.md);</span><span class="sxs-lookup"><span data-stu-id="e5f2f-135">Whether the assembly was found in the [global assembly cache](../app-domains/gac.md).</span></span>

    - <span data-ttu-id="e5f2f-136">список всех проверенных URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-136">A list of all probing URLs.</span></span>

<span data-ttu-id="e5f2f-137">Приведенная ниже запись журнала содержит подробные сведения об ошибке привязки сборки.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-137">The following sample log entry shows detailed information about a failed assembly bind.</span></span>

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="to-delete-a-single-entry-from-the-log"></a><span data-ttu-id="e5f2f-138">Удаление записи из журнала</span><span class="sxs-lookup"><span data-stu-id="e5f2f-138">To delete a single entry from the log</span></span>

1. <span data-ttu-id="e5f2f-139">Выберите запись в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-139">Select an entry in the viewer.</span></span>

2. <span data-ttu-id="e5f2f-140">Нажмите кнопку **Удалить запись**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-140">Click the **Delete Entry** button.</span></span>

### <a name="to-delete-all-entries-from-the-log"></a><span data-ttu-id="e5f2f-141">Удаление всех записей из журнала</span><span class="sxs-lookup"><span data-stu-id="e5f2f-141">To delete all entries from the log</span></span>

- <span data-ttu-id="e5f2f-142">Нажмите кнопку **Удалить все**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-142">Click the **Delete All** button.</span></span>

### <a name="to-refresh-the-user-interface"></a><span data-ttu-id="e5f2f-143">Обновление пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e5f2f-143">To refresh the user interface</span></span>

- <span data-ttu-id="e5f2f-144">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-144">Click the **Refresh** button.</span></span> <span data-ttu-id="e5f2f-145">Средство просмотра не выявляет новые записи во время работы автоматически.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-145">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="e5f2f-146">Чтобы показать эти записи, нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-146">You must use the **Refresh** button to display them.</span></span>

### <a name="to-change-the-log-settings"></a><span data-ttu-id="e5f2f-147">Изменение параметров журнала</span><span class="sxs-lookup"><span data-stu-id="e5f2f-147">To change the log settings</span></span>

- <span data-ttu-id="e5f2f-148">Нажмите кнопку **Параметры**, чтобы открыть диалоговое окно **Параметры журнала**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-148">Click the **Settings** button to open the **Log Settings** dialog.</span></span>

### <a name="to-view-the-about-dialog"></a><span data-ttu-id="e5f2f-149">Как открыть диалоговое окно сведений о программе</span><span class="sxs-lookup"><span data-stu-id="e5f2f-149">To view the About dialog</span></span>

- <span data-ttu-id="e5f2f-150">Нажмите кнопку **О программе**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-150">Click the **About** button.</span></span>

## <a name="binding-logs-for-native-images"></a><span data-ttu-id="e5f2f-151">Журналы привязки машинных образов</span><span class="sxs-lookup"><span data-stu-id="e5f2f-151">Binding Logs for Native Images</span></span>

<span data-ttu-id="e5f2f-152">По умолчанию средство Fuslogvw.exe записывает в журнал обычные запросы на привязку сборок.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-152">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="e5f2f-153">В журнал также можно включить привязки сборок для образов в машинном коде, созданных с помощью программы [Ngen.exe (генератор образов в машинном коде)](ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-153">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).</span></span>

#### <a name="to-log-assembly-binds-for-native-images"></a><span data-ttu-id="e5f2f-154">Запись в журнал привязок сборок машинных образов</span><span class="sxs-lookup"><span data-stu-id="e5f2f-154">To log assembly binds for native images</span></span>

- <span data-ttu-id="e5f2f-155">В группе **Категории журналов** выберите параметр **Образцы в машинном коде**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-155">In the **Log Categories** group, select the **Native Images** option button.</span></span>

<span data-ttu-id="e5f2f-156">Следующий журнал иллюстрирует ошибку, вызванную зависимостью, которая не существовала в момент создания для приложения машинного образа.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-156">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="e5f2f-157">Если зависимости во время выполнения отличаются от зависимостей при выполнении Ngen.exe, привязка к машинному образу не допускается.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-157">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

<span data-ttu-id="e5f2f-158">Следующий журнал иллюстрирует ошибку привязки машинного образа, вызванную различиями в настройках параметров безопасности при выполнении приложения и при создании машинного образа.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-158">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a><span data-ttu-id="e5f2f-159">Диалоговое окно "Параметры журнала"</span><span class="sxs-lookup"><span data-stu-id="e5f2f-159">The Log Settings Dialog</span></span>

<span data-ttu-id="e5f2f-160">В диалоговом окне **Параметры журнала** можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-160">You can use the **Log Settings** dialog to perform the following actions.</span></span>

#### <a name="to-disable-logging"></a><span data-ttu-id="e5f2f-161">Отключение ведения журнала</span><span class="sxs-lookup"><span data-stu-id="e5f2f-161">To disable logging</span></span>

- <span data-ttu-id="e5f2f-162">Выберите **Журнал отключен**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-162">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="e5f2f-163">Обратите внимание, что этот параметр выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-163">Note that this option is selected by default.</span></span>

#### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="e5f2f-164">Запись привязок сборок в исключения</span><span class="sxs-lookup"><span data-stu-id="e5f2f-164">To log assembly binds in exceptions</span></span>

- <span data-ttu-id="e5f2f-165">Выберите **Запись текста исключения в журнал**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-165">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="e5f2f-166">В тексте исключения указываются наиболее краткие сведения fusion-журнала.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-166">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="e5f2f-167">Чтобы просмотреть все сведения, используйте один из других параметров.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-167">To view full information, use one of the other settings.</span></span>

  <span data-ttu-id="e5f2f-168">См. важное примечание о сборках, которые загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-168">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="e5f2f-169">Запись в журнал ошибок привязки сборок</span><span class="sxs-lookup"><span data-stu-id="e5f2f-169">To log assembly bind failures</span></span>

- <span data-ttu-id="e5f2f-170">Выберите **Запись ошибок привязки на диск**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-170">Select the **Log bind failures to disk** option button.</span></span>

  <span data-ttu-id="e5f2f-171">См. важное примечание о сборках, которые загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-171">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="e5f2f-172">Запись в журнал всех привязок сборок</span><span class="sxs-lookup"><span data-stu-id="e5f2f-172">To log all assembly binds</span></span>

- <span data-ttu-id="e5f2f-173">Выберите **Запись всех привязок на диск**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-173">Select the **Log all binds to disk** option button.</span></span>

  <span data-ttu-id="e5f2f-174">См. важное примечание о сборках, которые загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-174">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5f2f-175">Если сборка загружается как нейтральная к домену, например если свойству <xref:System.AppDomainSetup.LoaderOptimization%2A> задано значение <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> или <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, в некоторых случаях ведение журнала может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-175">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="e5f2f-176">Это возможно, если запись вносится в журнал при загрузке нейтрального к домену модуля в домен приложения с последующей выгрузкой домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-176">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="e5f2f-177">Запись журнала может не освобождаться до завершения данного процесса.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-177">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="e5f2f-178">Некоторые отладчики включают ведение журналов автоматически.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-178">Some debuggers automatically turn on logging.</span></span>

#### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="e5f2f-179">Разрешение пользовательского пути к журналу</span><span class="sxs-lookup"><span data-stu-id="e5f2f-179">To enable a custom log path</span></span>

1. <span data-ttu-id="e5f2f-180">Выберите **Разрешить пользовательский путь к журналу**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-180">Select the **Enable custom log path** option button.</span></span>

2. <span data-ttu-id="e5f2f-181">Введите путь в текстовом поле **Пользовательский путь к журналу**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-181">Enter the path into the **Custom log path** text box.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f2f-182">[Средство просмотра журнала привязки сборок (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) сохраняет журнал привязок в кэше Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-182">The [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="e5f2f-183">Из-за возможных повреждений кэша Internet Explorer в окне [средства просмотра журнала привязок сборки (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) перестают отображаться новые журналы привязок.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-183">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="e5f2f-184">В результате таких сбоев инфраструктура привязки в платформе .NET (fusion) не может выполнять запись в журнал привязки и считывание из него.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-184">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="e5f2f-185">(Эта проблема не возникает при выборе пользовательского пути к журналу).  Чтобы fusion-журнал снова отображал привязки, очистите кэш IE. Для этого удалите временные файлы Интернета в диалоговом окне "Свойства обозревателя".</span><span class="sxs-lookup"><span data-stu-id="e5f2f-185">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>
>
> <span data-ttu-id="e5f2f-186">Если неуправляемое приложение размещает среду CLR посредством реализации интерфейсов `IHostAssemblyManager` и `IHostAssemblyStore`, хранение записей журнала в кэше WinINet невозможно.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-186">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span>  <span data-ttu-id="e5f2f-187">Чтобы просматривать записи журнала основных пользовательских приложений, которые реализуют эти интерфейсы, необходимо задать альтернативный путь к журналу.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-187">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="e5f2f-188">Ведение журнала для приложений, выполняемых в контейнере приложений Windows</span><span class="sxs-lookup"><span data-stu-id="e5f2f-188">To enable logging for apps running in the Windows app container</span></span>

1. <span data-ttu-id="e5f2f-189">Укажите пользовательский путь к журналу, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-189">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="e5f2f-190">По умолчанию у приложений, выполняемых в контейнере приложений Windows, ограничен доступ к жесткому диску.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-190">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="e5f2f-191">Все приложения в контейнере приложений будут иметь право на чтение и запись в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-191">The directory you specify will have read/write access for all apps in the app container.</span></span>

2. <span data-ttu-id="e5f2f-192">Установите флажок **Включить иммерсивное ведение журнала**.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-192">Select the **Enable immersive logging** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5f2f-193">Это поле активно только в Windows 8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-193">This box is enabled only on Windows 8 or later.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5f2f-194">См. также</span><span class="sxs-lookup"><span data-stu-id="e5f2f-194">See also</span></span>

- <xref:System.TypeLoadException>
- [<span data-ttu-id="e5f2f-195">Инструменты</span><span class="sxs-lookup"><span data-stu-id="e5f2f-195">Tools</span></span>](index.md)
- [<span data-ttu-id="e5f2f-196">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="e5f2f-196">Global Assembly Cache</span></span>](../app-domains/gac.md)
- [<span data-ttu-id="e5f2f-197">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="e5f2f-197">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="e5f2f-198">Командные строки</span><span class="sxs-lookup"><span data-stu-id="e5f2f-198">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
