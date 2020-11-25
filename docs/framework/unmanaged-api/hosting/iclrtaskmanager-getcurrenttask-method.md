---
title: Метод ICLRTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: af855e3ba47dc329a4fb722c3e13d5f1816beba4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723281"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="0ee25-102">Метод ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="0ee25-102">ICLRTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="0ee25-103">Возвращает экземпляр [ICLRTask](iclrtask-interface.md) , который в данный момент выполняется в потоке операционной системы, из которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="0ee25-103">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ee25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ee25-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ee25-105">Parameters</span></span>  

 `ppTask`  
 <span data-ttu-id="0ee25-106">заполняет Указатель на адрес `ICLRTask` экземпляра, который в данный момент выполняется в потоке операционной системы, из которого был получен вызов, или значение null, если в данном потоке не выполняется ни одной задачи.</span><span class="sxs-lookup"><span data-stu-id="0ee25-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ee25-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0ee25-107">Return Value</span></span>  
  
|<span data-ttu-id="0ee25-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ee25-108">HRESULT</span></span>|<span data-ttu-id="0ee25-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="0ee25-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ee25-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ee25-110">S_OK</span></span>|<span data-ttu-id="0ee25-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="0ee25-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="0ee25-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ee25-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ee25-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0ee25-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ee25-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ee25-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ee25-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0ee25-115">The call timed out.</span></span>|  
|<span data-ttu-id="0ee25-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ee25-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ee25-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0ee25-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ee25-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ee25-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ee25-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0ee25-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ee25-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ee25-120">E_FAIL</span></span>|<span data-ttu-id="0ee25-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0ee25-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ee25-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0ee25-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ee25-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0ee25-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ee25-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0ee25-124">Remarks</span></span>  

 <span data-ttu-id="0ee25-125">`ICLRTask`Экземпляр, на который `ppTask` указывает параметр, представляет выполняемую в данный момент задачу для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0ee25-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="0ee25-126">`ICLRTask`Экземпляр связан с соответствующим экземпляром [IHostTask](ihosttask-interface.md) , представляющим задачу для узла.</span><span class="sxs-lookup"><span data-stu-id="0ee25-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee25-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0ee25-127">Requirements</span></span>  

 <span data-ttu-id="0ee25-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ee25-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee25-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0ee25-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ee25-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ee25-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ee25-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee25-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee25-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0ee25-132">See also</span></span>

- [<span data-ttu-id="0ee25-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0ee25-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0ee25-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0ee25-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0ee25-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="0ee25-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0ee25-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0ee25-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
