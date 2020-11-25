---
title: Метод IHostIoCompletionManager::CreateIoCompletionPort
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: 0c74e073d55ab7dc98620052a0cfd68c294f7a1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724277"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="3a2af-102">Метод IHostIoCompletionManager::CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="3a2af-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>

<span data-ttu-id="3a2af-103">Запрашивает создание узлом нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="3a2af-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a2af-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a2af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a2af-105">Parameters</span></span>  

 `phPort`  
 <span data-ttu-id="3a2af-106">заполняет Указатель на обработчик для вновь созданного порта завершения ввода-вывода или 0 (нуль), если не удалось создать порт.</span><span class="sxs-lookup"><span data-stu-id="3a2af-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a2af-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a2af-107">Return Value</span></span>  
  
|<span data-ttu-id="3a2af-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a2af-108">HRESULT</span></span>|<span data-ttu-id="3a2af-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="3a2af-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a2af-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a2af-110">S_OK</span></span>|<span data-ttu-id="3a2af-111">`CreateIoCompletionPort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3a2af-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="3a2af-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a2af-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a2af-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3a2af-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a2af-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a2af-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a2af-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="3a2af-115">The call timed out.</span></span>|  
|<span data-ttu-id="3a2af-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a2af-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a2af-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="3a2af-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a2af-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a2af-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a2af-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="3a2af-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a2af-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a2af-120">E_FAIL</span></span>|<span data-ttu-id="3a2af-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3a2af-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a2af-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3a2af-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a2af-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3a2af-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3a2af-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3a2af-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3a2af-125">Недостаточно памяти для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="3a2af-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a2af-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3a2af-126">Remarks</span></span>  

 <span data-ttu-id="3a2af-127">Среда CLR вызывает `CreateIoCompletionPort` метод, чтобы запросить создание узлом нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="3a2af-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="3a2af-128">Он привязывает операции ввода-вывода к этому порту с помощью вызова метода [IHostIoCompletionManager:: BIND](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3a2af-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="3a2af-129">Узел сообщает среде CLR о состоянии, вызывая [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="3a2af-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2af-130">Требования</span><span class="sxs-lookup"><span data-stu-id="3a2af-130">Requirements</span></span>  

 <span data-ttu-id="3a2af-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a2af-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a2af-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3a2af-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a2af-133">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a2af-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a2af-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a2af-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2af-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3a2af-135">See also</span></span>

- [<span data-ttu-id="3a2af-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="3a2af-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3a2af-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="3a2af-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
