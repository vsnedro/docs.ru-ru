---
title: Метод IHostAssemblyStore::ProvideModule
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: 002f4177f19c2aae99e91e3fe1029b81e17481dc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805009"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="8ef1a-102">Метод IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="8ef1a-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="8ef1a-103">Разрешает модуль в сборке или связанном (но не внедренном) файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ef1a-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ef1a-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="8ef1a-106">окне Указатель на экземпляр [модулебиндинфо](modulebindinfo-structure.md) , который описывает имя запрашиваемого модуля <xref:System.AppDomain> , сборки и имени модуля.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-106">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="8ef1a-107">заполняет Указатель на уникальный идентификатор для `IStream` содержащего загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="8ef1a-108">заполняет Указатель на адрес `IStream` объекта, который содержит загружаемый переносимый исполняемый файл (PE), или значение null, если не удалось найти модуль.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="8ef1a-109">заполняет Указатель на адрес `IStream` объекта, который содержит сведения об отладке программы (PDB) для запрошенного модуля, или значение null, если PDB-файл найти не удалось.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ef1a-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8ef1a-110">Return Value</span></span>  
  
|<span data-ttu-id="8ef1a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ef1a-111">HRESULT</span></span>|<span data-ttu-id="8ef1a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8ef1a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ef1a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ef1a-113">S_OK</span></span>|<span data-ttu-id="8ef1a-114">`ProvideModule`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="8ef1a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ef1a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ef1a-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ef1a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ef1a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ef1a-118">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-118">The call timed out.</span></span>|  
|<span data-ttu-id="8ef1a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ef1a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ef1a-120">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ef1a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ef1a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ef1a-122">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ef1a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ef1a-123">E_FAIL</span></span>|<span data-ttu-id="8ef1a-124">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ef1a-125">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ef1a-126">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ef1a-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="8ef1a-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="8ef1a-128">Не удалось найти запрошенную сборку или связанный ресурс.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="8ef1a-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8ef1a-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8ef1a-130">`pdwModuleId`недостаточно велик, чтобы вместить идентификатор, который требуется вернуть узлу.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ef1a-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="8ef1a-131">Remarks</span></span>  
 <span data-ttu-id="8ef1a-132">Значение идентификатора, возвращенное для `pdwModuleId` , задается узлом.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="8ef1a-133">Идентификаторы должны быть уникальными в течение всего времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="8ef1a-134">Среда CLR использует это значение в качестве уникального идентификатора для связанного потока.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="8ef1a-135">Он проверяет каждое значение по значениям `pAssemblyId` , возвращаемым вызовами [провидеассембли](ihostassemblystore-provideassembly-method.md) , и значениями, `pdwModuleId` возвращаемыми другими вызовами метода `ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="8ef1a-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="8ef1a-136">Если узел возвращает одно и то же значение идентификатора для другого `IStream` , среда CLR проверяет, было ли уже сопоставлено содержимое этого потока.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="8ef1a-137">Если это так, среда CLR загружает существующую копию изображения вместо сопоставления нового.</span><span class="sxs-lookup"><span data-stu-id="8ef1a-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="8ef1a-138">Таким образом, идентификатор также не должен перекрываться с идентификаторами сборок, возвращенными из `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="8ef1a-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef1a-139">Требования</span><span class="sxs-lookup"><span data-stu-id="8ef1a-139">Requirements</span></span>  
 <span data-ttu-id="8ef1a-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ef1a-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef1a-141">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8ef1a-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ef1a-142">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8ef1a-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ef1a-143">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ef1a-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef1a-144">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8ef1a-144">See also</span></span>

- [<span data-ttu-id="8ef1a-145">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="8ef1a-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8ef1a-146">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="8ef1a-146">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="8ef1a-147">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="8ef1a-147">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
