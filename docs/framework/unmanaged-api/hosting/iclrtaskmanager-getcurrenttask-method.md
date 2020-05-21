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
ms.openlocfilehash: 9cb97d9f383b7b54b431457042c4c4a7fc9cd876
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762837"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="ab118-102">Метод ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="ab118-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="ab118-103">Возвращает экземпляр [ICLRTask](iclrtask-interface.md) , который в данный момент выполняется в потоке операционной системы, из которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="ab118-103">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab118-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab118-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab118-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab118-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="ab118-106">заполняет Указатель на адрес `ICLRTask` экземпляра, который в данный момент выполняется в потоке операционной системы, из которого был получен вызов, или значение null, если в данном потоке не выполняется ни одной задачи.</span><span class="sxs-lookup"><span data-stu-id="ab118-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab118-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab118-107">Return Value</span></span>  
  
|<span data-ttu-id="ab118-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab118-108">HRESULT</span></span>|<span data-ttu-id="ab118-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ab118-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab118-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab118-110">S_OK</span></span>|<span data-ttu-id="ab118-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="ab118-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="ab118-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab118-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab118-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ab118-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab118-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab118-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab118-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ab118-115">The call timed out.</span></span>|  
|<span data-ttu-id="ab118-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab118-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab118-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ab118-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab118-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab118-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab118-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ab118-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab118-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab118-120">E_FAIL</span></span>|<span data-ttu-id="ab118-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ab118-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab118-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ab118-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab118-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ab118-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab118-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ab118-124">Remarks</span></span>  
 <span data-ttu-id="ab118-125">`ICLRTask`Экземпляр, на который `ppTask` указывает параметр, представляет выполняемую в данный момент задачу для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ab118-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="ab118-126">`ICLRTask`Экземпляр связан с соответствующим экземпляром [IHostTask](ihosttask-interface.md) , представляющим задачу для узла.</span><span class="sxs-lookup"><span data-stu-id="ab118-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab118-127">Требования</span><span class="sxs-lookup"><span data-stu-id="ab118-127">Requirements</span></span>  
 <span data-ttu-id="ab118-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab118-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab118-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ab118-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab118-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ab118-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab118-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab118-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab118-132">См. также</span><span class="sxs-lookup"><span data-stu-id="ab118-132">See also</span></span>

- [<span data-ttu-id="ab118-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ab118-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ab118-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ab118-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ab118-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ab118-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ab118-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ab118-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
