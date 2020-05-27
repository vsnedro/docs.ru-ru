---
title: Метод IHostSecurityManager::SetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 79ef08ef70ad1132ceacc3e2b997651e57032b9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803807"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="5cd69-102">Метод IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="5cd69-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="5cd69-103">Задает контекст безопасности выполняемого в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="5cd69-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cd69-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cd69-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="5cd69-106">окне Одно из значений [еконтексттипе](econtexttype-enumeration.md) , указывающее, какой тип контекста используется средой CLR для размещения на узле.</span><span class="sxs-lookup"><span data-stu-id="5cd69-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="5cd69-107">заполняет Указатель на адрес нового объекта [IHostSecurityContext](ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5cd69-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cd69-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5cd69-108">Return Value</span></span>  
  
|<span data-ttu-id="5cd69-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cd69-109">HRESULT</span></span>|<span data-ttu-id="5cd69-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd69-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cd69-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cd69-111">S_OK</span></span>|<span data-ttu-id="5cd69-112">`SetSecurityContext`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="5cd69-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="5cd69-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5cd69-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5cd69-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5cd69-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5cd69-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5cd69-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5cd69-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5cd69-116">The call timed out.</span></span>|  
|<span data-ttu-id="5cd69-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5cd69-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5cd69-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5cd69-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5cd69-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5cd69-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5cd69-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5cd69-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5cd69-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5cd69-121">E_FAIL</span></span>|<span data-ttu-id="5cd69-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5cd69-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5cd69-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5cd69-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5cd69-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5cd69-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cd69-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="5cd69-125">Remarks</span></span>  
 <span data-ttu-id="5cd69-126">Среда CLR вызывает `SetSecurityContext` в нескольких сценариях.</span><span class="sxs-lookup"><span data-stu-id="5cd69-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="5cd69-127">Перед выполнением конструкторов классов и модулей и методов завершения среда CLR вызывает `SetSecurityContext` для защиты узла от сбоев при выполнении.</span><span class="sxs-lookup"><span data-stu-id="5cd69-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="5cd69-128">Затем он сбрасывает контекст безопасности до исходного состояния после выполнения конструктора или метода завершения, используя другой вызов `SetSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="5cd69-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="5cd69-129">Аналогичный шаблон происходит при завершении ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="5cd69-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="5cd69-130">Если узел реализует [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), среда CLR вызывает `SetSecurityContext` после того, как узел вызывает [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="5cd69-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="5cd69-131">В асинхронных точках рабочих потоков среда CLR вызывает `SetSecurityContext` в <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> или внутри [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)в зависимости от того, РЕАЛИЗУЕТ ли узел или CLR пул потоков.</span><span class="sxs-lookup"><span data-stu-id="5cd69-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cd69-132">Требования</span><span class="sxs-lookup"><span data-stu-id="5cd69-132">Requirements</span></span>  
 <span data-ttu-id="5cd69-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd69-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cd69-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5cd69-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cd69-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5cd69-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cd69-136">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd69-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd69-137">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5cd69-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="5cd69-138">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="5cd69-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="5cd69-139">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="5cd69-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5cd69-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="5cd69-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="5cd69-141">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="5cd69-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="5cd69-142">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="5cd69-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="5cd69-143">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="5cd69-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
