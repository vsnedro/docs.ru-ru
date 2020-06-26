---
title: Диагностика ошибок посредством управляемых помощников по отладке
description: Диагностика ошибок в .NET с помощью помощников по отладке управляемого кода. Помощники MDA — это средства отладки, работающие совместно с CLR для предоставления сведений о состоянии среды выполнения.
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
ms.openlocfilehash: ac6fdc09fb057cc55659ce076d37ab96fe2354d1
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416100"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="2eb22-104">Диагностика ошибок с помощью помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="2eb22-104">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="2eb22-105">Помощники отладки управляемого кода (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для предоставления информации о состоянии времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-105">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="2eb22-106">Эти помощники формируют информационные сообщения о событиях времени выполнения, которые вы не можете зафиксировать иными средствами.</span><span class="sxs-lookup"><span data-stu-id="2eb22-106">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="2eb22-107">Вы можете использовать помощники отладки управляемого кода для изоляции тяжело обнаружимых ошибок приложения, возникающих при переходе между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="2eb22-107">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="2eb22-108">Вы можете [включить или отключить](#enable-and-disable-mdas) все MDA, добавив ключ в реестр Windows или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="2eb22-108">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="2eb22-109">Вы можете включить отдельные помощники, используя параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-109">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="2eb22-110">Вы можете задать дополнительные параметры для некоторых отдельных помощников в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-110">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="2eb22-111">Поскольку эти файлы конфигурации анализируются при загрузке среды выполнения, следует включить помощник до запуска управляемого приложения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-111">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="2eb22-112">Вы не сможете включить его для уже запущенных приложений.</span><span class="sxs-lookup"><span data-stu-id="2eb22-112">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="2eb22-113">В следующей таблице перечислены MDA, поставляемые с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2eb22-113">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="2eb22-114">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="2eb22-114">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="2eb22-115">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="2eb22-115">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="2eb22-116">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="2eb22-116">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="2eb22-117">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="2eb22-117">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="2eb22-118">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="2eb22-118">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="2eb22-119">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="2eb22-119">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="2eb22-120">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="2eb22-120">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="2eb22-121">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="2eb22-121">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="2eb22-122">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="2eb22-122">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="2eb22-123">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="2eb22-123">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="2eb22-124">failedQI</span><span class="sxs-lookup"><span data-stu-id="2eb22-124">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="2eb22-125">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="2eb22-125">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="2eb22-126">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="2eb22-126">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="2eb22-127">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="2eb22-127">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="2eb22-128">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="2eb22-128">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="2eb22-129">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="2eb22-129">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="2eb22-130">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="2eb22-130">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="2eb22-131">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="2eb22-131">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="2eb22-132">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="2eb22-132">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="2eb22-133">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="2eb22-133">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="2eb22-134">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="2eb22-134">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="2eb22-135">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="2eb22-135">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="2eb22-136">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="2eb22-136">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="2eb22-137">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="2eb22-137">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="2eb22-138">loaderLock</span><span class="sxs-lookup"><span data-stu-id="2eb22-138">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="2eb22-139">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="2eb22-139">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="2eb22-140">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="2eb22-140">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="2eb22-141">marshaling</span><span class="sxs-lookup"><span data-stu-id="2eb22-141">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="2eb22-142">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="2eb22-142">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="2eb22-143">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="2eb22-143">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="2eb22-144">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="2eb22-144">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="2eb22-145">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="2eb22-145">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="2eb22-146">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="2eb22-146">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="2eb22-147">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="2eb22-147">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="2eb22-148">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="2eb22-148">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="2eb22-149">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="2eb22-149">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="2eb22-150">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="2eb22-150">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="2eb22-151">повторного входа</span><span class="sxs-lookup"><span data-stu-id="2eb22-151">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="2eb22-152">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="2eb22-152">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="2eb22-153">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="2eb22-153">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="2eb22-154">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="2eb22-154">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="2eb22-155">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="2eb22-155">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="2eb22-156">По умолчанию .NET Framework активирует подмножество помощников отладки управляемого кода для всех управляемых отладчиков.</span><span class="sxs-lookup"><span data-stu-id="2eb22-156">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="2eb22-157">Вы можете просмотреть набор по умолчанию в Visual Studio, **Windows**выбрав пункт  >  **параметры исключений** Windows в меню **Отладка** , а затем развернув список **помощники по отладке управляемого** кода.</span><span class="sxs-lookup"><span data-stu-id="2eb22-157">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Окно параметров исключений в Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="2eb22-159">Включение и отключение MDA</span><span class="sxs-lookup"><span data-stu-id="2eb22-159">Enable and Disable MDAs</span></span>

<span data-ttu-id="2eb22-160">Вы можете включать и отключать помощники отладки управляемого кода с помощью раздела реестра, переменной среды и параметров конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-160">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="2eb22-161">Чтобы воспользоваться параметрами конфигурации приложения, вы должны включить раздел реестра или переменную среды.</span><span class="sxs-lookup"><span data-stu-id="2eb22-161">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="2eb22-162">Вместо отключения MDA можно запретить Visual Studio отображать диалоговое окно MDA при получении уведомления MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-162">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="2eb22-163">Для этого выберите **Windows**  >  **параметры исключений** Windows в меню **Отладка** , разверните список **помощники по отладке управляемого** кода, а затем установите или снимите флажок **прерывать при возникновении** для отдельного MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-163">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="2eb22-164">Ключ реестра</span><span class="sxs-lookup"><span data-stu-id="2eb22-164">Registry Key</span></span>

<span data-ttu-id="2eb22-165">Чтобы включить MDA, добавьте **HKEY_LOCAL_MACHINE \софтваре\микрософт \\ . Подраздел Нетфрамеворк\мда** (введите REG_SZ, значение 1) в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="2eb22-165">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="2eb22-166">Скопируйте следующий пример в текстовый файл с именем *мдаенабле. reg*. Откройте редактор реестра Windows (RegEdit.exe) и в меню **файл** выберите пункт **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="2eb22-166">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="2eb22-167">Выберите файл *мдаенабле. reg* , чтобы включить MDA на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2eb22-167">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="2eb22-168">При установке подраздела в строковое значение **1** (а не значение DWORD, равное **1**) включает чтение параметров MDA из файла *ApplicationName. суффикса*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2eb22-168">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="2eb22-169">Например, файл конфигурации MDA для блокнота будет называться notepad.exe.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2eb22-169">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="2eb22-170">Если на компьютере в 64-разрядной операционной системе выполнянется 32-разрядное приложение, раздел помощника нужно задать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2eb22-170">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="2eb22-171">Дополнительные сведения см. в разделе [Параметры конфигурации, относящиеся к приложению](#application-specific-configuration-settings) .</span><span class="sxs-lookup"><span data-stu-id="2eb22-171">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="2eb22-172">Этот параметр реестра может быть перезаписан переменной среды COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-172">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="2eb22-173">Дополнительные сведения см. в разделе [переменная среды](#environment-variable) .</span><span class="sxs-lookup"><span data-stu-id="2eb22-173">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="2eb22-174">Чтобы отключить MDA, присвойте подразделу MDA значение **0** (ноль) с помощью редактора реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="2eb22-174">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="2eb22-175">По умолчанию некоторые помощники отладки управляемого кода включаются при запуске приложения, подключенного к отладчику, даже без добавления раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="2eb22-175">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="2eb22-176">Эти помощники можно отключить, запустив файл *мдадисабле. reg* , как описано выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2eb22-176">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="2eb22-177">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="2eb22-177">Environment Variable</span></span>

<span data-ttu-id="2eb22-178">Активацией помощников также можно управлять с помощью переменной среды COMPLUS_MDA, которая переопределяет раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="2eb22-178">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="2eb22-179">Строка COMPLUS_MDA представляет собой разделенный точками с запятыми перечень имен помощников отладки управляемого кода или других специальных управляющих строк, составленный без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="2eb22-179">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="2eb22-180">При запуске под контролем управляемого или неуправляемого отладчика по умолчанию включается набор помощников.</span><span class="sxs-lookup"><span data-stu-id="2eb22-180">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="2eb22-181">Для этого необходимо неявным образом добавить разделенный точками с запятыми список помощников, которые включаются по умолчанию под контролем отладчиков, в начало значения переменной среды или раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="2eb22-181">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="2eb22-182">Специальные управляющие строки:</span><span class="sxs-lookup"><span data-stu-id="2eb22-182">The special control strings are the following:</span></span>

- <span data-ttu-id="2eb22-183">`0` — отключает все помощники.</span><span class="sxs-lookup"><span data-stu-id="2eb22-183">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="2eb22-184">`1` — считывает параметры помощника из файла *ИмяПриложения*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2eb22-184">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="2eb22-185">`managedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске управляемого исполняемого файла под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="2eb22-185">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="2eb22-186">`unmanagedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске неуправляемого исполняемого файла под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="2eb22-186">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="2eb22-187">При наличии конфликтующих параметров более старые параметры переопределяются более новыми:</span><span class="sxs-lookup"><span data-stu-id="2eb22-187">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="2eb22-188">`COMPLUS_MDA=0` отключает все помощники, включая те, которые неявно включаются под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="2eb22-188">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="2eb22-189">`COMPLUS_MDA=gcUnmanagedToManaged` включает `gcUnmanagedToManaged` в дополнение к помощникам, которые неявно включаются под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="2eb22-189">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="2eb22-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` включает `gcUnmanagedToManaged`, но отключает те помощники, которые были бы неявно включены под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="2eb22-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="2eb22-191">Параметры конфигурации для конкретного приложения</span><span class="sxs-lookup"><span data-stu-id="2eb22-191">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="2eb22-192">Вы можете включать, отключать и настраивать некоторые помощники по отдельности в файле конфигурации помощников отладки управляемого кода для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-192">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="2eb22-193">Чтобы разрешить использование файла конфигурации приложения для настройки помощников, необходимо задать раздел реестра или переменную среды COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-193">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="2eb22-194">Файл конфигурации приложения обычно находится в одном каталоге с исполняемым файлом (EXE) приложения.</span><span class="sxs-lookup"><span data-stu-id="2eb22-194">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="2eb22-195">Имя файла имеет форму *ApplicationName*.mda.config; Например, notepad.exe.mda.config. У помощников, включенных в файле конфигурации приложения, могут быть атрибуты или элементы, специально предназначенные для управления поведением этого помощника.</span><span class="sxs-lookup"><span data-stu-id="2eb22-195">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="2eb22-196">В следующем примере показано, как включить и настроить [упаковку](marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="2eb22-196">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

<span data-ttu-id="2eb22-197">Помощник отладки управляемого кода `Marshaling` выдает информацию об управляемом типе, который маршалируется в неуправляемый тип для каждого перехода между управляемым и неуправляемым кодом в приложении.</span><span class="sxs-lookup"><span data-stu-id="2eb22-197">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="2eb22-198">`Marshaling`MDA также может фильтровать имена методов и полей структуры, предоставляемых в дочерних элементах **Месодфилтер** и **фиелдфилтер** соответственно.</span><span class="sxs-lookup"><span data-stu-id="2eb22-198">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="2eb22-199">В следующем примере показано, как включить несколько MDA с помощью параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eb22-199">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> <span data-ttu-id="2eb22-200">При указании нескольких помощников в файле конфигурации их следует перечислять в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="2eb22-200">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="2eb22-201">Например, если вы хотите включить помощники `virtualCERCall` и `invalidCERCall`, необходимо добавить запись `<invalidCERCall />` перед записью `<virtualCERCall />`.</span><span class="sxs-lookup"><span data-stu-id="2eb22-201">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="2eb22-202">Если записи расположены не в алфавитном порядке, отображается сообщение о необработанном исключении недопустимого файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2eb22-202">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="2eb22-203">Исключения MDA</span><span class="sxs-lookup"><span data-stu-id="2eb22-203">MDA exceptions</span></span>

<span data-ttu-id="2eb22-204">Если MDA включен, он активен даже в том случае, если код не выполняется в отладчике.</span><span class="sxs-lookup"><span data-stu-id="2eb22-204">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="2eb22-205">Если событие помощника отладки управляемого кода возникает при отсутствии отладчика, сообщений события выводится в диалоговом окне необработанного исключения, хотя оно и не является необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="2eb22-205">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="2eb22-206">Чтобы предотвратить появление диалогового окна, удаляйте параметр, отвечающий за включение помощника, когда ваш код не выполняется в среде отладки.</span><span class="sxs-lookup"><span data-stu-id="2eb22-206">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="2eb22-207">Когда код выполняется в интегрированной среде разработки Visual Studio (IDE), можно избежать диалогового окна исключения, которое отображается для конкретных событий MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-207">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="2eb22-208">Для этого в меню **Отладка** выберите пункт **Windows**  >  **параметры исключений**Windows.</span><span class="sxs-lookup"><span data-stu-id="2eb22-208">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="2eb22-209">В окне **параметры исключений** разверните список **помощники по отладке управляемого** кода, а затем снимите флажок **прерывать при возникновении** для отдельного MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-209">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="2eb22-210">Это диалоговое окно также можно использовать, чтобы *включить* отображение диалоговых окон исключений MDA.</span><span class="sxs-lookup"><span data-stu-id="2eb22-210">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="2eb22-211">Выходные данные помощников</span><span class="sxs-lookup"><span data-stu-id="2eb22-211">MDA Output</span></span>

<span data-ttu-id="2eb22-212">Выходные данные MDA похожи на приведенный ниже пример, который показывает выходные данные `PInvokeStackImbalance` помощника по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="2eb22-212">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="2eb22-213">**Вызов функции PInvoke "Мдатест! Мдатест. Program:: StdCall ' имеет несбалансированный стек. Скорее всего, это связано с тем, что управляемая сигнатура PInvoke не соответствует неуправляемой сигнатуре целевого объекта. Убедитесь, что соглашение о вызовах и параметры сигнатуры PInvoke соответствуют целевой неуправляемой подписи.**</span><span class="sxs-lookup"><span data-stu-id="2eb22-213">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="2eb22-214">См. также</span><span class="sxs-lookup"><span data-stu-id="2eb22-214">See also</span></span>

- [<span data-ttu-id="2eb22-215">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="2eb22-215">Debugging, Tracing, and Profiling</span></span>](index.md)
