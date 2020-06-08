---
title: Функция CorBindToRuntimeEx
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
ms.openlocfilehash: e66b63ffa4ed25e861cff6bd9eb6065f57ff807f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493504"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="05046-102">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="05046-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="05046-103">Позволяет неуправляемым узлам загружать среду CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="05046-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="05046-104">[CorBindToRuntime](corbindtoruntime-function.md) и `CorBindToRuntimeEx` функции выполняют одну и ту же операцию, но `CorBindToRuntimeEx` функция позволяет устанавливать флаги для указания поведения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="05046-104">The [CorBindToRuntime](corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="05046-105">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="05046-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="05046-106">Эта функция принимает набор параметров, позволяющих узлу выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="05046-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="05046-107">Укажите версию среды выполнения, которая будет загружена.</span><span class="sxs-lookup"><span data-stu-id="05046-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="05046-108">Укажите, следует ли загружать сборку сервера или рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="05046-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="05046-109">Управление тем, выполняется ли параллельная сборка мусора или не параллельная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="05046-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05046-110">Параллельная сборка мусора не поддерживается в приложениях, использующих Эмулятор WOW64 x86 в 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64).</span><span class="sxs-lookup"><span data-stu-id="05046-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="05046-111">Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows см. в разделе [выполнение 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="05046-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="05046-112">Определяет, загружаются ли сборки как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="05046-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="05046-113">Получите указатель интерфейса на [ICorRuntimeHost](icorruntimehost-interface.md) , который можно использовать для установки дополнительных параметров для настройки экземпляра среды CLR перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="05046-113">Obtain an interface pointer to an [ICorRuntimeHost](icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05046-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05046-114">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05046-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="05046-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="05046-116">окне Строка, описывающая версию среды CLR, которую требуется загрузить.</span><span class="sxs-lookup"><span data-stu-id="05046-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="05046-117">Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *основной. дополнительный. сборка. Редакция*.</span><span class="sxs-lookup"><span data-stu-id="05046-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="05046-118">Строка, передаваемая как, `pwszVersion` должна начинаться с символа "v", за которым следуют первые три части номера версии (например, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="05046-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="05046-119">Некоторые версии среды CLR устанавливаются с инструкцией политики, которая определяет совместимость с предыдущими версиями среды CLR.</span><span class="sxs-lookup"><span data-stu-id="05046-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="05046-120">По умолчанию оболочка запуска выполняет проверку на `pwszVersion` соответствие инструкциям политики и загружает последнюю версию среды выполнения, совместимую с запрашиваемой версией.</span><span class="sxs-lookup"><span data-stu-id="05046-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="05046-121">Узел может заставить оболочку пропускать вычисление политики и загружать точную версию, указанную в `pwszVersion` , передав значение `STARTUP_LOADER_SAFEMODE` для `startupFlags` параметра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="05046-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="05046-122">Если вызывающий объект задает значение NULL для `pwszVersion` , `CorBindToRuntimeEx` определяет набор установленных сред выполнения, Номера версий которых ниже среды выполнения .NET Framework 4, и загружают последнюю версию среды выполнения из этого набора.</span><span class="sxs-lookup"><span data-stu-id="05046-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="05046-123">Он не загружает .NET Framework 4 или более поздней версии и завершается ошибкой, если предыдущая версия не установлена.</span><span class="sxs-lookup"><span data-stu-id="05046-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="05046-124">Обратите внимание, что передача значения NULL позволяет узлу не контролировать, какая версия среды выполнения загружена.</span><span class="sxs-lookup"><span data-stu-id="05046-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="05046-125">Хотя такой подход может быть приемлемым в некоторых сценариях, настоятельно рекомендуется, чтобы узел предоставил определенную версию для загрузки.</span><span class="sxs-lookup"><span data-stu-id="05046-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="05046-126">окне Строка, указывающая, загружать ли сервер или рабочую станцию сборку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="05046-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="05046-127">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="05046-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="05046-128">Сборка сервера оптимизирована для использования нескольких процессоров для сборок мусора, а сборка рабочей станции оптимизирована для клиентских приложений, работающих на однопроцессорном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05046-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="05046-129">Если параметр `pwszBuildFlavor` имеет значение null, загружается сборка рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="05046-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="05046-130">При запуске на однопроцессорном компьютере сборка рабочей станции всегда загружается, даже если параметр `pwszBuildFlavor` имеет значение `svr` .</span><span class="sxs-lookup"><span data-stu-id="05046-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="05046-131">Однако если задано `pwszBuildFlavor` значение `svr` и задана параллельная сборка мусора (см `startupFlags` . Описание параметра), то загружается серверная сборка.</span><span class="sxs-lookup"><span data-stu-id="05046-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="05046-132">окне Сочетание значений перечисления [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="05046-132">[in] A combination of values of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="05046-133">Эти флаги контролируют параллельную сборку мусора, код, нейтральный к домену, и поведение `pwszVersion` параметра.</span><span class="sxs-lookup"><span data-stu-id="05046-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="05046-134">Значение по умолчанию — один домен, если флаг не установлен.</span><span class="sxs-lookup"><span data-stu-id="05046-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="05046-135">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="05046-135">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="05046-136">Описание этих флагов см. в разделе Перечисление [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="05046-136">For descriptions of these flags, see the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="05046-137">окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) или [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="05046-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="05046-138">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="05046-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="05046-139">окне Объект `IID` запрашиваемого интерфейса из `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="05046-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="05046-140">Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="05046-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="05046-141">заполняет Возвращаемый указатель интерфейса в `riid` .</span><span class="sxs-lookup"><span data-stu-id="05046-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05046-142">Примечания</span><span class="sxs-lookup"><span data-stu-id="05046-142">Remarks</span></span>  
 <span data-ttu-id="05046-143">Если `pwszVersion` указывает несуществующую версию среды выполнения, `CorBindToRuntimeEx` ВОЗВРАЩАЕТ значение HRESULT, равное CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="05046-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="05046-144">Контекст выполнения и поток удостоверения Windows</span><span class="sxs-lookup"><span data-stu-id="05046-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="05046-145">В версии 1 среды CLR <xref:System.Security.Principal.WindowsIdentity> объект не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера.</span><span class="sxs-lookup"><span data-stu-id="05046-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="05046-146">В версии 2,0 среды CLR <xref:System.Threading.ExecutionContext> объект заключает некоторые сведения о выполняемом в данный момент потоке и передает его через любую асинхронную точку, но не через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="05046-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="05046-147">Аналогичным образом <xref:System.Security.Principal.WindowsIdentity> объект также проходит через любую асинхронную точку.</span><span class="sxs-lookup"><span data-stu-id="05046-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="05046-148">Таким образом, текущее олицетворение в потоке, если таковое имеется, также проходит.</span><span class="sxs-lookup"><span data-stu-id="05046-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="05046-149">Изменить последовательность можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="05046-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="05046-150">Путем изменения <xref:System.Threading.ExecutionContext> параметров для подавления потока на основе потока (см <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> . методы, и).</span><span class="sxs-lookup"><span data-stu-id="05046-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="05046-151">Изменив режим обработки по умолчанию на режим совместимости версии 1, где <xref:System.Security.Principal.WindowsIdentity> объект не пополняется по какой бы то ни было асинхронной точке, независимо от <xref:System.Threading.ExecutionContext> параметров в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="05046-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="05046-152">Изменение режима по умолчанию зависит от того, используется ли управляемый исполняемый файл или неуправляемый интерфейс размещения для загрузки среды CLR:</span><span class="sxs-lookup"><span data-stu-id="05046-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="05046-153">Для управляемых исполняемых файлов необходимо задать `enabled` атрибуту [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) элемента значение `true` .</span><span class="sxs-lookup"><span data-stu-id="05046-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="05046-154">Для неуправляемых интерфейсов размещения установите `STARTUP_LEGACY_IMPERSONATION` флаг в `startupFlags` параметре при вызове `CorBindToRuntimeEx` функции.</span><span class="sxs-lookup"><span data-stu-id="05046-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="05046-155">Режим совместимости версии 1 применяется ко всему процессу и всем доменам приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="05046-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05046-156">Требования</span><span class="sxs-lookup"><span data-stu-id="05046-156">Requirements</span></span>  
 <span data-ttu-id="05046-157">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05046-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05046-158">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="05046-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05046-159">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="05046-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05046-160">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05046-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05046-161">См. также</span><span class="sxs-lookup"><span data-stu-id="05046-161">See also</span></span>

- [<span data-ttu-id="05046-162">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="05046-162">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="05046-163">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="05046-163">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="05046-164">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="05046-164">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="05046-165">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="05046-165">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="05046-166">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="05046-166">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="05046-167">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="05046-167">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
