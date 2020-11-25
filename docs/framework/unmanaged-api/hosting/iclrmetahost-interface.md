---
title: Интерфейс ICLRMetaHost
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: 75c8d550e572795a291f4639f9f28bd5214ff188
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714020"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="3d84a-102">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="3d84a-102">ICLRMetaHost Interface</span></span>

<span data-ttu-id="3d84a-103">Предоставляет методы, возвращающие определенную версию среды CLR на основе ее номера версии, список всех установленных CLR, список всех сред выполнения, загруженных в указанный процесс, обнаружение версии среды CLR, используемой для компиляции сборки, выхода из процесса с чистым завершением работы среды выполнения и запроса привязки API прежних версий.</span><span class="sxs-lookup"><span data-stu-id="3d84a-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d84a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3d84a-104">Methods</span></span>  
  
|<span data-ttu-id="3d84a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3d84a-105">Method</span></span>|<span data-ttu-id="3d84a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3d84a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d84a-107">Метод EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="3d84a-107">EnumerateInstalledRuntimes Method</span></span>](iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="3d84a-108">Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой версии среды CLR, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d84a-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="3d84a-109">Метод EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="3d84a-109">EnumerateLoadedRuntimes Method</span></span>](iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="3d84a-110">Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой среды CLR, загруженной в заданный процесс.</span><span class="sxs-lookup"><span data-stu-id="3d84a-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="3d84a-111">Этот метод заменяет [GetVersionFromProcess](getversionfromprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="3d84a-111">This method supersedes [GetVersionFromProcess](getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="3d84a-112">Метод ExitProcess</span><span class="sxs-lookup"><span data-stu-id="3d84a-112">ExitProcess Method</span></span>](iclrmetahost-exitprocess-method.md)|<span data-ttu-id="3d84a-113">Пытается корректно завершить работу всех загруженных сред выполнения, а затем завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="3d84a-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="3d84a-114">Заменяет функцию [корекситпроцесс](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="3d84a-114">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="3d84a-115">Метод GetRuntime</span><span class="sxs-lookup"><span data-stu-id="3d84a-115">GetRuntime Method</span></span>](iclrmetahost-getruntime-method.md)|<span data-ttu-id="3d84a-116">Возвращает интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующий определенной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3d84a-116">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="3d84a-117">Этот метод заменяет функцию [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , используемую с флагом [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3d84a-117">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="3d84a-118">Метод GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="3d84a-118">GetVersionFromFile Method</span></span>](iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="3d84a-119">Возвращает исходную версию компиляции .NET Framework сборки (хранится в метаданных) по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="3d84a-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="3d84a-120">Этот метод заменяет [жетфилеверсион](getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="3d84a-120">This method supersedes [GetFileVersion](getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="3d84a-121">Метод QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="3d84a-121">QueryLegacyV2RuntimeBinding Method</span></span>](iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="3d84a-122">Возвращает интерфейс, представляющий среду выполнения, к которой привязана политика устаревшей активации, например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута в записи файла конфигурации [ \<startup> элемента](../../configure-apps/file-schema/startup/startup-element.md) , путем непосредственного использования устаревших API-интерфейсов активации или путем вызова метода [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3d84a-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="3d84a-123">Метод RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="3d84a-123">RequestRuntimeLoadedNotification Method</span></span>](iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="3d84a-124">Гарантирует обратный вызов к указанному указателю функции при первой загрузке версии среды CLR, но еще не запущенной.</span><span class="sxs-lookup"><span data-stu-id="3d84a-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="3d84a-125">Этот метод заменяет [локкклрверсион](lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="3d84a-125">This method supersedes [LockClrVersion](lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d84a-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3d84a-126">Remarks</span></span>  

 <span data-ttu-id="3d84a-127">Единственный способ получить экземпляр этого интерфейса — вызвать функцию [клркреатеинстанце](clrcreateinstance-function.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d84a-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3d84a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="3d84a-128">Requirements</span></span>  

 <span data-ttu-id="3d84a-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d84a-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d84a-130">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="3d84a-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3d84a-131">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d84a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d84a-132">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d84a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d84a-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d84a-133">See also</span></span>

- [<span data-ttu-id="3d84a-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3d84a-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3d84a-135">Размещение</span><span class="sxs-lookup"><span data-stu-id="3d84a-135">Hosting</span></span>](index.md)
