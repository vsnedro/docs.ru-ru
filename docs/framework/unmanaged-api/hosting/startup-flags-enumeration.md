---
title: Перечисление STARTUP_FLAGS
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
ms.openlocfilehash: b4694efffa0a3dd6fed1f97fc2359c5eb335d440
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006419"
---
# <a name="startup_flags-enumeration"></a><span data-ttu-id="65901-102">Перечисление STARTUP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="65901-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="65901-103">Содержит значения, которые указывают на поведение среды CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="65901-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="65901-104">По умолчанию сборка мусора не параллельна, и в область, нейтральную к домену, загружается только Библиотека базовых классов.</span><span class="sxs-lookup"><span data-stu-id="65901-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65901-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65901-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="65901-106">Участники</span><span class="sxs-lookup"><span data-stu-id="65901-106">Members</span></span>  
  
|<span data-ttu-id="65901-107">Член</span><span class="sxs-lookup"><span data-stu-id="65901-107">Member</span></span>|<span data-ttu-id="65901-108">Описание</span><span class="sxs-lookup"><span data-stu-id="65901-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="65901-109">Указывает, что следует использовать параллельную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="65901-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="65901-110">Если вызывающий объект запрашивает сборку сервера и параллельную сборку мусора на однопроцессорном компьютере, то выполняется сборка рабочей станции и непараллельная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="65901-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="65901-111">**Примечание.**  Параллельная сборка мусора не поддерживается в приложениях, работающих под управлением эмулятора x86 WOW64 в 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64).</span><span class="sxs-lookup"><span data-stu-id="65901-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="65901-112">Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows см. в разделе [выполнение 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="65901-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="65901-113">Указывает, что должна выполняться оптимизация загрузчика.</span><span class="sxs-lookup"><span data-stu-id="65901-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="65901-114">Указывает, что ни одна сборка не загружается как нейтральная к домену.</span><span class="sxs-lookup"><span data-stu-id="65901-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="65901-115">Указывает, что все сборки загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="65901-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="65901-116">Указывает, что все сборки со строгими именами загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="65901-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="65901-117">Указывает, что политика версий среды CLR не будет применена к переданной версии.</span><span class="sxs-lookup"><span data-stu-id="65901-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="65901-118">Будет загружена точная версия, указанная для CLR.</span><span class="sxs-lookup"><span data-stu-id="65901-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="65901-119">Оболочка совместимости не выполняет оценку политики для определения последней совместимой версии.</span><span class="sxs-lookup"><span data-stu-id="65901-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="65901-120">Указывает, что предпочтительная среда выполнения будет установлена, но фактически не запущена.</span><span class="sxs-lookup"><span data-stu-id="65901-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="65901-121">Указывает, что будет использоваться сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="65901-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="65901-122">Указывает, что виртуальный адрес будет использоваться при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="65901-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="65901-123">Указывает, что смешивание интерфейса размещения не будет разрешено.</span><span class="sxs-lookup"><span data-stu-id="65901-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="65901-124">Указывает, что олицетворение не должно проходить через асинхронные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65901-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="65901-125">Указывает, что весь стек потоков не должен зафиксироваться при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="65901-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="65901-126">Указывает, что управляемые олицетворения и олицетворения, полученные через вызов неуправляемого кода, будут передаваться через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="65901-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="65901-127">По умолчанию только управляемые олицетворения будут проходить через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="65901-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="65901-128">Указывает, что при нехватке системной памяти сборка мусора будет использовать меньше зафиксированного пространства.</span><span class="sxs-lookup"><span data-stu-id="65901-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="65901-129">См `gcTrimCommitOnLowMemory` . раздел [Оптимизация для размещения общих веб-](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md)сайтов.</span><span class="sxs-lookup"><span data-stu-id="65901-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="65901-130">Указывает, что трассировка событий для Windows (ETW) включена для событий общеязыковой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="65901-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="65901-131">Начиная с Windows Vista, трассировка событий всегда включена, поэтому этот флаг не действует.</span><span class="sxs-lookup"><span data-stu-id="65901-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="65901-132">См. раздел [Управление ведением журнала .NET Framework](../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="65901-132">See [Controlling .NET Framework Logging](../../performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="65901-133">Указывает, что отслеживание ресурсов домена приложения включено.</span><span class="sxs-lookup"><span data-stu-id="65901-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="65901-134">См <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> . свойство и [ \<appDomainResourceMonitoring> элемент](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span><span class="sxs-lookup"><span data-stu-id="65901-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65901-135">Требования</span><span class="sxs-lookup"><span data-stu-id="65901-135">Requirements</span></span>  
 <span data-ttu-id="65901-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65901-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65901-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="65901-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65901-138">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="65901-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65901-139">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65901-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65901-140">См. также статью</span><span class="sxs-lookup"><span data-stu-id="65901-140">See also</span></span>

- [<span data-ttu-id="65901-141">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="65901-141">Hosting Enumerations</span></span>](hosting-enumerations.md)
