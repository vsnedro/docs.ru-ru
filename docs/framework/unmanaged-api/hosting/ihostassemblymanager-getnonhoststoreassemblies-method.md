---
title: Метод IHostAssemblyManager::GetNonHostStoreAssemblies
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
ms.openlocfilehash: 9a1440be7011130b16d7112ae15026eb74856190
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501603"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="86948-102">Метод IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="86948-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="86948-103">Возвращает указатель интерфейса на объект [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые должны загружаться хостом в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="86948-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86948-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86948-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86948-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86948-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="86948-106">заполняет Указатель на адрес объекта `ICLRAssemblyReferenceList` , содержащий список ссылок на сборки, которые узел загружает в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="86948-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86948-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86948-107">Return Value</span></span>  
  
|<span data-ttu-id="86948-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86948-108">HRESULT</span></span>|<span data-ttu-id="86948-109">Описание</span><span class="sxs-lookup"><span data-stu-id="86948-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86948-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="86948-110">S_OK</span></span>|<span data-ttu-id="86948-111">`GetNonHostStoreAssemblies`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="86948-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="86948-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86948-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86948-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="86948-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86948-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86948-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86948-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="86948-115">The call timed out.</span></span>|  
|<span data-ttu-id="86948-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86948-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86948-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="86948-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86948-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86948-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86948-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="86948-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86948-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86948-120">E_FAIL</span></span>|<span data-ttu-id="86948-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="86948-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86948-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="86948-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86948-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86948-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="86948-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="86948-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="86948-125">Недостаточно свободной памяти для создания списка ссылок для запрошенного объекта `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="86948-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86948-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="86948-126">Remarks</span></span>  
 <span data-ttu-id="86948-127">Среда CLR разрешает ссылки с помощью следующего набора рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="86948-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="86948-128">Во первых, он обращается к списку ссылок на сборки, возвращаемых `GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="86948-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="86948-129">Если сборка отображается в списке, среда CLR привязывает ее к обычному.</span><span class="sxs-lookup"><span data-stu-id="86948-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="86948-130">Если сборка не отображается в списке и узел предоставил реализацию [IHostAssemblyStore](ihostassemblystore-interface.md), среда CLR вызывает [IHostAssemblyStore::P ровидеассембли](ihostassemblystore-provideassembly-method.md) , чтобы разрешить узлу предоставить сборку для привязки.</span><span class="sxs-lookup"><span data-stu-id="86948-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="86948-131">В противном случае среда CLR не сможет выполнить привязку к сборке.</span><span class="sxs-lookup"><span data-stu-id="86948-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="86948-132">Если узел `ppReferenceList` имеет значение null, среда CLR сначала проверяет глобальный кэш сборок, вызывает `ProvideAssembly` , а затем проверяет базу приложения для разрешения ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="86948-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86948-133">После инициализации среда CLR вызывает `GetNonHostStoreAssemblies` только один раз.</span><span class="sxs-lookup"><span data-stu-id="86948-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="86948-134">Метод не вызывается снова.</span><span class="sxs-lookup"><span data-stu-id="86948-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86948-135">Требования</span><span class="sxs-lookup"><span data-stu-id="86948-135">Requirements</span></span>  
 <span data-ttu-id="86948-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86948-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86948-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="86948-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86948-138">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="86948-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86948-139">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86948-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86948-140">См. также</span><span class="sxs-lookup"><span data-stu-id="86948-140">See also</span></span>

- [<span data-ttu-id="86948-141">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="86948-141">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="86948-142">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="86948-142">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="86948-143">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="86948-143">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
