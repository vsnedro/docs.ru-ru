---
title: Метод IHostControl::GetHostManager
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
ms.openlocfilehash: 25e931ec17cad3508d548fb4ca7e53b0ade3f119
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804951"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="2913f-102">Метод IHostControl::GetHostManager</span><span class="sxs-lookup"><span data-stu-id="2913f-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="2913f-103">Возвращает указатель интерфейса на реализацию интерфейса узла с указанным `IID` .</span><span class="sxs-lookup"><span data-stu-id="2913f-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2913f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2913f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2913f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2913f-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="2913f-106">окне `IID`Интерфейс, для которого запрашиваются общеязыковая среда выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="2913f-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="2913f-107">заполняет Указатель на интерфейс, реализуемый узлом, или значение null, если узел не поддерживает этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2913f-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2913f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2913f-108">Return Value</span></span>  
  
|<span data-ttu-id="2913f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2913f-109">HRESULT</span></span>|<span data-ttu-id="2913f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2913f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2913f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2913f-111">S_OK</span></span>|<span data-ttu-id="2913f-112">`GetHostManager`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2913f-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="2913f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2913f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2913f-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2913f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2913f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2913f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2913f-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2913f-116">The call timed out.</span></span>|  
|<span data-ttu-id="2913f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2913f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2913f-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2913f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2913f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2913f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2913f-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2913f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2913f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2913f-121">E_FAIL</span></span>|<span data-ttu-id="2913f-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2913f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2913f-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2913f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2913f-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2913f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2913f-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2913f-125">E_INVALIDARG</span></span>|<span data-ttu-id="2913f-126">Запрошен `IID` недопустимый.</span><span class="sxs-lookup"><span data-stu-id="2913f-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="2913f-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="2913f-127">E_NOINTERFACE</span></span>|<span data-ttu-id="2913f-128">Запрошенный интерфейс не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2913f-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2913f-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="2913f-129">Remarks</span></span>  
 <span data-ttu-id="2913f-130">Среда CLR опрашивает узел, чтобы определить, поддерживает ли он один или несколько следующих интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="2913f-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="2913f-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="2913f-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="2913f-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2913f-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="2913f-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="2913f-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="2913f-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2913f-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="2913f-135">Метод ihostsyncmanager</span><span class="sxs-lookup"><span data-stu-id="2913f-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="2913f-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="2913f-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="2913f-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="2913f-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="2913f-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="2913f-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="2913f-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="2913f-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="2913f-140">Если узел поддерживает указанный интерфейс, он задает `ppObject` его реализацию этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2913f-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="2913f-141">В противном случае устанавливается `ppObject` значение null.</span><span class="sxs-lookup"><span data-stu-id="2913f-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="2913f-142">Среда CLR не вызывает `Release` диспетчеры узлов даже при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="2913f-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2913f-143">Требования</span><span class="sxs-lookup"><span data-stu-id="2913f-143">Requirements</span></span>  
 <span data-ttu-id="2913f-144">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2913f-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2913f-145">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2913f-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2913f-146">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2913f-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2913f-147">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2913f-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2913f-148">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2913f-148">See also</span></span>

- [<span data-ttu-id="2913f-149">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="2913f-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
