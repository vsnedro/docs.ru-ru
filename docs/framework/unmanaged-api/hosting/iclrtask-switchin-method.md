---
title: Метод ICLRTask::SwitchIn
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: d8f57af459d1bb3f338cfbfcbb29f69f533ea927
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762933"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="f4305-102">Метод ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="f4305-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="f4305-103">Уведомляет среду CLR о том, что задача, которую представляет текущий экземпляр [ICLRTask](iclrtask-interface.md) , теперь находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="f4305-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4305-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4305-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4305-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4305-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="f4305-106">окне Маркер физического потока, в котором выполняются задачи, представленные текущим `ICLRTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="f4305-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4305-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f4305-107">Return Value</span></span>  
  
|<span data-ttu-id="f4305-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4305-108">HRESULT</span></span>|<span data-ttu-id="f4305-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f4305-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4305-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4305-110">S_OK</span></span>|<span data-ttu-id="f4305-111">`SwitchIn`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f4305-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="f4305-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4305-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4305-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f4305-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4305-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4305-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4305-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f4305-115">The call timed out.</span></span>|  
|<span data-ttu-id="f4305-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4305-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4305-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f4305-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4305-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4305-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4305-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f4305-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4305-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4305-120">E_FAIL</span></span>|<span data-ttu-id="f4305-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f4305-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4305-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f4305-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4305-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f4305-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f4305-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="f4305-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="f4305-125">`SwitchIn`был вызван без предыдущего вызова [метода Switch](iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4305-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4305-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f4305-126">Remarks</span></span>  
 <span data-ttu-id="f4305-127">`threadHandle`Параметр представляет собой обработчик для потока операционной системы, в котором запланирована задача, представленная текущим `ICLRTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="f4305-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="f4305-128">Если в этом потоке возникло олицетворение, то перед переключением в задаче необходимо вызвать метод [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f4305-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4305-129">Вызов метода `SwitchIn` без предыдущего вызова `SwitchOut` завершается ошибкой со значением HRESULT, равным HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="f4305-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4305-130">Требования</span><span class="sxs-lookup"><span data-stu-id="f4305-130">Requirements</span></span>  
 <span data-ttu-id="f4305-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4305-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4305-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4305-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4305-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4305-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4305-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4305-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4305-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f4305-135">See also</span></span>

- [<span data-ttu-id="f4305-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f4305-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f4305-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f4305-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f4305-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f4305-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f4305-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f4305-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
