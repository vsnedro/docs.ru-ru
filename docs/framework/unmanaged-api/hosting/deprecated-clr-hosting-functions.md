---
title: Устаревшие функции размещения CLR
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504372"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="f84cf-102">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f84cf-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="f84cf-103">В этом разделе описаны неуправляемые глобальные статические функции, которые использовались в предыдущих версиях API размещения.</span><span class="sxs-lookup"><span data-stu-id="f84cf-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="f84cf-104">За исключением функций инфраструктуры ( `_Cor*` функций), которые используются только .NET Framework, эти функции являются устаревшими в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f84cf-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="f84cf-105">Функции активации</span><span class="sxs-lookup"><span data-stu-id="f84cf-105">Activation functions</span></span>  
 [<span data-ttu-id="f84cf-106">Функция ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="f84cf-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="f84cf-107">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-107">Deprecated.</span></span> <span data-ttu-id="f84cf-108">Создает экземпляр указанного управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="f84cf-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="f84cf-109">Функция CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="f84cf-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="f84cf-110">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="f84cf-110">Obsolete.</span></span> <span data-ttu-id="f84cf-111">Чтобы инициализировать среду CLR, используйте либо [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , либо [корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="f84cf-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="f84cf-112">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="f84cf-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="f84cf-113">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-113">Deprecated.</span></span> <span data-ttu-id="f84cf-114">Гарантирует, что подсистема выполнения среды CLR загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="f84cf-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="f84cf-115">Используйте вместо этого метод [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f84cf-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="f84cf-116">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="f84cf-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="f84cf-117">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-117">Deprecated.</span></span> <span data-ttu-id="f84cf-118">Загружает среду CLR в процесс с использованием сведений о версии, хранящихся в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="f84cf-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="f84cf-119">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="f84cf-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="f84cf-120">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-120">Deprecated.</span></span> <span data-ttu-id="f84cf-121">Позволяет неуправляемым узлам загружать среду CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="f84cf-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="f84cf-122">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="f84cf-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="f84cf-123">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-123">Deprecated.</span></span> <span data-ttu-id="f84cf-124">Загружает среду CLR в процесс с использованием сведений о версии, считываемых из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="f84cf-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="f84cf-125">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="f84cf-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="f84cf-126">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-126">Deprecated.</span></span> <span data-ttu-id="f84cf-127">Позволяет неуправляемым узлам загружать среду CLR в процесс и устанавливать флаги для указания поведения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f84cf-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="f84cf-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f84cf-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="f84cf-129">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-129">Deprecated.</span></span> <span data-ttu-id="f84cf-130">Позволяет узлам загружать указанную версию среды CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="f84cf-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="f84cf-131">Функция GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="f84cf-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="f84cf-132">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-132">Deprecated.</span></span> <span data-ttu-id="f84cf-133">Возвращает требуемый номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f84cf-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="f84cf-134">Функция GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="f84cf-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="f84cf-135">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-135">Deprecated.</span></span> <span data-ttu-id="f84cf-136">Возвращает каталог установки CLR, который загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="f84cf-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="f84cf-137">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="f84cf-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="f84cf-138">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-138">Deprecated.</span></span> <span data-ttu-id="f84cf-139">Возвращает адрес указанной функции, которая экспортируется из последней установленной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f84cf-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="f84cf-140">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f84cf-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="f84cf-141">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-141">Deprecated.</span></span> <span data-ttu-id="f84cf-142">Возвращает сведения о версии и каталоге о среде CLR, запрошенной приложением.</span><span class="sxs-lookup"><span data-stu-id="f84cf-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="f84cf-143">Функции версий среды CLR</span><span class="sxs-lookup"><span data-stu-id="f84cf-143">CLR version functions</span></span>  
 <span data-ttu-id="f84cf-144">Функции в этом разделе возвращают версию среды CLR. они не активируют среду CLR.</span><span class="sxs-lookup"><span data-stu-id="f84cf-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="f84cf-145">Функция GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="f84cf-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="f84cf-146">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-146">Deprecated.</span></span> <span data-ttu-id="f84cf-147">Возвращает номер версии среды CLR, которая выполняется в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="f84cf-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="f84cf-148">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="f84cf-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="f84cf-149">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-149">Deprecated.</span></span> <span data-ttu-id="f84cf-150">Возвращает сведения о версии среды CLR указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="f84cf-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="f84cf-151">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="f84cf-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="f84cf-152">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-152">Deprecated.</span></span> <span data-ttu-id="f84cf-153">Возвращает номер версии среды CLR, запрошенной указанным приложением.</span><span class="sxs-lookup"><span data-stu-id="f84cf-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="f84cf-154">Если эта версия не установлена, возвращает последнюю версию, установленную до запрошенной версии.</span><span class="sxs-lookup"><span data-stu-id="f84cf-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="f84cf-155">Функция GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="f84cf-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="f84cf-156">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-156">Deprecated.</span></span> <span data-ttu-id="f84cf-157">Возвращает соответствующую информацию о версии среды CLR для класса с указанным идентификатором CLSID.</span><span class="sxs-lookup"><span data-stu-id="f84cf-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="f84cf-158">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="f84cf-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="f84cf-159">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-159">Deprecated.</span></span> <span data-ttu-id="f84cf-160">Возвращает номер версии среды CLR, связанной с указанным обработчиком процесса.</span><span class="sxs-lookup"><span data-stu-id="f84cf-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="f84cf-161">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="f84cf-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="f84cf-162">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-162">Deprecated.</span></span> <span data-ttu-id="f84cf-163">Позволяет узлу определить версию среды CLR, которая будет использоваться в процессе перед явной инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f84cf-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="f84cf-164">Функции размещения</span><span class="sxs-lookup"><span data-stu-id="f84cf-164">Hosting functions</span></span>  
 [<span data-ttu-id="f84cf-165">Функция CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="f84cf-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="f84cf-166">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-166">Deprecated.</span></span> <span data-ttu-id="f84cf-167">Вызывает функцию с указанным именем и параметрами в указанной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="f84cf-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="f84cf-168">Функция CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="f84cf-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="f84cf-169">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-169">Deprecated.</span></span> <span data-ttu-id="f84cf-170">Выгружает сборку COM из процесса.</span><span class="sxs-lookup"><span data-stu-id="f84cf-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="f84cf-171">Функция CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="f84cf-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="f84cf-172">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-172">Deprecated.</span></span> <span data-ttu-id="f84cf-173">Завершает текущий неуправляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="f84cf-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="f84cf-174">Функция CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="f84cf-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="f84cf-175">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-175">Deprecated.</span></span> <span data-ttu-id="f84cf-176">Запускает приложение по указанному сетевому пути, используя указанные манифесты и другие данные приложения.</span><span class="sxs-lookup"><span data-stu-id="f84cf-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="f84cf-177">Функция CorMarkThreadInThreadPool</span><span class="sxs-lookup"><span data-stu-id="f84cf-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="f84cf-178">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-178">Deprecated.</span></span> <span data-ttu-id="f84cf-179">Помечает выполняющийся в данный момент поток пула потоков для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f84cf-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="f84cf-180">Начиная с версии .NET Framework 2,0 эта функция не действует.</span><span class="sxs-lookup"><span data-stu-id="f84cf-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="f84cf-181">Он не является обязательным и может быть удален из кода.</span><span class="sxs-lookup"><span data-stu-id="f84cf-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="f84cf-182">Функция CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="f84cf-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="f84cf-183">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="f84cf-183">Obsolete.</span></span> <span data-ttu-id="f84cf-184">Среду CLR нельзя выгрузить из процесса.</span><span class="sxs-lookup"><span data-stu-id="f84cf-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="f84cf-185">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="f84cf-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="f84cf-186">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="f84cf-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="f84cf-187">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="f84cf-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="f84cf-188">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-188">Deprecated.</span></span> <span data-ttu-id="f84cf-189">Создает объект [ICorDebug](../debugging/icordebug-interface.md) на основе указанных сведений о версии.</span><span class="sxs-lookup"><span data-stu-id="f84cf-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="f84cf-190">Функция CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="f84cf-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="f84cf-191">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-191">Deprecated.</span></span> <span data-ttu-id="f84cf-192">Создает объект [ицеефилежен](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="f84cf-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="f84cf-193">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="f84cf-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="f84cf-194">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-194">Deprecated.</span></span> <span data-ttu-id="f84cf-195">Уничтожает объект [ицеефилежен](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="f84cf-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="f84cf-196">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="f84cf-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="f84cf-197">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-197">Deprecated.</span></span> <span data-ttu-id="f84cf-198">Указывает на функцию, которую CLR вызывает для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f84cf-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="f84cf-199">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="f84cf-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="f84cf-200">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-200">Deprecated.</span></span> <span data-ttu-id="f84cf-201">Указывает на функцию, которая вызывается средой CLR для уведомления узла о том, что инициализация запущена или завершена.</span><span class="sxs-lookup"><span data-stu-id="f84cf-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="f84cf-202">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f84cf-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="f84cf-203">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-203">Deprecated.</span></span> <span data-ttu-id="f84cf-204">Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="f84cf-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="f84cf-205">Функция LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="f84cf-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="f84cf-206">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-206">Deprecated.</span></span> <span data-ttu-id="f84cf-207">Загружает указанную версию .NET Framework DLL.</span><span class="sxs-lookup"><span data-stu-id="f84cf-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="f84cf-208">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="f84cf-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="f84cf-209">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-209">Deprecated.</span></span> <span data-ttu-id="f84cf-210">Преобразует значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.</span><span class="sxs-lookup"><span data-stu-id="f84cf-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="f84cf-211">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="f84cf-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="f84cf-212">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-212">Deprecated.</span></span> <span data-ttu-id="f84cf-213">Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="f84cf-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="f84cf-214">Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="f84cf-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="f84cf-215">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-215">Deprecated.</span></span> <span data-ttu-id="f84cf-216">Указывает на функцию, которая уведомляет узел при завершении перекрытия (асинхронного) ввода-вывода на устройство.</span><span class="sxs-lookup"><span data-stu-id="f84cf-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="f84cf-217">Указатель функции LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="f84cf-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="f84cf-218">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-218">Deprecated.</span></span> <span data-ttu-id="f84cf-219">Указывает на функцию, которая уведомляет узел о начале выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="f84cf-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="f84cf-220">Функция RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="f84cf-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="f84cf-221">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-221">Deprecated.</span></span> <span data-ttu-id="f84cf-222">Выполняет указанную команду.</span><span class="sxs-lookup"><span data-stu-id="f84cf-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="f84cf-223">Указатель функции WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="f84cf-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="f84cf-224">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f84cf-224">Deprecated.</span></span> <span data-ttu-id="f84cf-225">Указывает на функцию, которая уведомляет узел о том, что дескриптор ожидания имеет сигнал или время ожидания истекло.</span><span class="sxs-lookup"><span data-stu-id="f84cf-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="f84cf-226">Функции инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="f84cf-226">Infrastructure functions</span></span>  
 <span data-ttu-id="f84cf-227">Функции в этом разделе предназначены для использования только .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f84cf-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="f84cf-228">Функция _CorDllMain</span><span class="sxs-lookup"><span data-stu-id="f84cf-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="f84cf-229">Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="f84cf-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="f84cf-230">Функция _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="f84cf-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="f84cf-231">Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="f84cf-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="f84cf-232">Функция _CorExeMain2</span><span class="sxs-lookup"><span data-stu-id="f84cf-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="f84cf-233">Выполняет точку входа в указанном коде, сопоставленном с памятью.</span><span class="sxs-lookup"><span data-stu-id="f84cf-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="f84cf-234">Эта функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f84cf-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="f84cf-235">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="f84cf-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="f84cf-236">Уведомляет загрузчик об выгрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="f84cf-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="f84cf-237">Функция _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="f84cf-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="f84cf-238">Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.</span><span class="sxs-lookup"><span data-stu-id="f84cf-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84cf-239">См. также</span><span class="sxs-lookup"><span data-stu-id="f84cf-239">See also</span></span>

- [<span data-ttu-id="f84cf-240">Глобальные статические функции размещения платформы .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="f84cf-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
