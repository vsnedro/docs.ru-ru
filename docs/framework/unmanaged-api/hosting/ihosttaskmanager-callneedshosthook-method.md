---
title: Метод IHostTaskManager::CallNeedsHostHook
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 5bc5752d4d2b772b1d18f438c4daaa1b8938da9e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842352"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="aa7ae-102">Метод IHostTaskManager::CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="aa7ae-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="aa7ae-103">Позволяет узлу указать, может ли среда CLR подставляема указанный вызов к неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa7ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa7ae-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa7ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa7ae-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="aa7ae-106">окне Адрес в сопоставленном переносимом исполняемом файле (PE) неуправляемой функции, которая должна быть вызвана.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="aa7ae-107">заполняет Указатель на логическое значение, указывающее, требует ли узел вызова метода.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa7ae-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aa7ae-108">Return Value</span></span>  
  
|<span data-ttu-id="aa7ae-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa7ae-109">HRESULT</span></span>|<span data-ttu-id="aa7ae-110">Описание</span><span class="sxs-lookup"><span data-stu-id="aa7ae-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa7ae-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa7ae-111">S_OK</span></span>|<span data-ttu-id="aa7ae-112">`CallNeedsHostHook`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="aa7ae-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa7ae-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa7ae-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa7ae-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa7ae-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aa7ae-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-116">The call timed out.</span></span>|  
|<span data-ttu-id="aa7ae-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa7ae-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aa7ae-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aa7ae-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aa7ae-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aa7ae-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aa7ae-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa7ae-121">E_FAIL</span></span>|<span data-ttu-id="aa7ae-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="aa7ae-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa7ae-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa7ae-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa7ae-125">Remarks</span></span>  
 <span data-ttu-id="aa7ae-126">Чтобы помочь оптимизировать выполнение кода, среда CLR выполняет анализ каждого вызова неиспользуемой платформы во время компиляции, чтобы определить, можно ли выполнить встраивание вызова.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="aa7ae-127">`CallNeedsHostHook`позволяет узлу переопределить это решение, запрашивая вызов неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="aa7ae-128">Если узлу требуется обработчик, среда выполнения не выполняет встраивание вызова.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="aa7ae-129">Обычно хосту требуется обработчик, в котором необходимо настроить состояние с плавающей запятой, или при получении уведомления о том, что вызов переходит в состояние, в котором узел не может отрегулировать запросы среды выполнения для памяти или какие-либо блокировки.</span><span class="sxs-lookup"><span data-stu-id="aa7ae-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="aa7ae-130">Когда узел требует, чтобы вызов был подключен, среда выполнения уведомляет узел о переходах к управляемому коду и из него с помощью вызовов [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [леаверунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [реверсинтеррунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)и [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="aa7ae-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa7ae-131">Требования</span><span class="sxs-lookup"><span data-stu-id="aa7ae-131">Requirements</span></span>  
 <span data-ttu-id="aa7ae-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa7ae-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa7ae-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aa7ae-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa7ae-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa7ae-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa7ae-135">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa7ae-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7ae-136">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="aa7ae-136">See also</span></span>

- [<span data-ttu-id="aa7ae-137">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="aa7ae-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="aa7ae-138">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="aa7ae-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="aa7ae-139">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="aa7ae-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="aa7ae-140">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="aa7ae-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
