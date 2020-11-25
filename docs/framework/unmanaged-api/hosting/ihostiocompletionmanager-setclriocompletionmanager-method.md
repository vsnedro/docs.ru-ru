---
title: Метод IHostIoCompletionManager::SetCLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
ms.openlocfilehash: d370cc81942269bd79e06e0fa57fe5d79832b3c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724849"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="65e15-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="65e15-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>

<span data-ttu-id="65e15-103">Предоставляет узлу указатель интерфейса на экземпляр [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) , реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="65e15-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65e15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65e15-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65e15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65e15-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="65e15-106">окне Указатель интерфейса на экземпляр, `ICLRIoCompletionManager` предоставляемый средой CLR.</span><span class="sxs-lookup"><span data-stu-id="65e15-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65e15-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65e15-107">Return Value</span></span>  
  
|<span data-ttu-id="65e15-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65e15-108">HRESULT</span></span>|<span data-ttu-id="65e15-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="65e15-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65e15-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="65e15-110">S_OK</span></span>|<span data-ttu-id="65e15-111">`SetCLRIoCompletionManager` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="65e15-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="65e15-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65e15-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65e15-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="65e15-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65e15-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65e15-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65e15-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="65e15-115">The call timed out.</span></span>|  
|<span data-ttu-id="65e15-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65e15-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65e15-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="65e15-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65e15-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65e15-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65e15-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="65e15-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65e15-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65e15-120">E_FAIL</span></span>|<span data-ttu-id="65e15-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="65e15-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65e15-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="65e15-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65e15-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="65e15-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65e15-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="65e15-124">Remarks</span></span>  

 <span data-ttu-id="65e15-125">После вызова CLR `SetCLRIoCompletionManager` узел должен вызвать [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) , чтобы уведомить CLR о завершении запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="65e15-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65e15-126">Требования</span><span class="sxs-lookup"><span data-stu-id="65e15-126">Requirements</span></span>  

 <span data-ttu-id="65e15-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65e15-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65e15-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="65e15-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65e15-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65e15-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65e15-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65e15-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65e15-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65e15-131">See also</span></span>

- [<span data-ttu-id="65e15-132">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="65e15-132">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="65e15-133">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="65e15-133">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
