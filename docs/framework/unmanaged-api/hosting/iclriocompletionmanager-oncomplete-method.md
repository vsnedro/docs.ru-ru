---
title: Метод ICLRIoCompletionManager::OnComplete
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: 15119974acf74b49669e5ffbee59fbff9e5c84c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714111"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="f6311-102">Метод ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="f6311-102">ICLRIoCompletionManager::OnComplete Method</span></span>

<span data-ttu-id="f6311-103">Уведомляет среду CLR о состоянии запроса ввода-вывода, выполненного с помощью вызова метода [IHostIoCompletionManager:: BIND](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f6311-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6311-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6311-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6311-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6311-105">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="f6311-106">окне Значение HRESULT, указывающее состояние операции привязки.</span><span class="sxs-lookup"><span data-stu-id="f6311-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="f6311-107">S_OK указывает, что операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="f6311-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="f6311-108">HOST_E_INTERRUPTED указывает, что вызов прерван до завершения.</span><span class="sxs-lookup"><span data-stu-id="f6311-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="f6311-109">E_FAIL указывает, что произошла неизвестная, Неустранимая фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f6311-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="f6311-110">окне Число байтов, передаваемых во время обработки запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="f6311-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="f6311-111">окне Указатель на `OVERLAPPED` структуру, которая была передана в вызов `IHostIoCompletionManager::Bind` метода.</span><span class="sxs-lookup"><span data-stu-id="f6311-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6311-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f6311-112">Return Value</span></span>  
  
|<span data-ttu-id="f6311-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6311-113">HRESULT</span></span>|<span data-ttu-id="f6311-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="f6311-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6311-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6311-115">S_OK</span></span>|<span data-ttu-id="f6311-116">`OnComplete` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f6311-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="f6311-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6311-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6311-118">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f6311-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6311-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6311-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6311-120">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f6311-120">The call timed out.</span></span>|  
|<span data-ttu-id="f6311-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6311-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6311-122">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f6311-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6311-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6311-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6311-124">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f6311-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6311-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6311-125">E_FAIL</span></span>|<span data-ttu-id="f6311-126">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f6311-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6311-127">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f6311-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6311-128">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6311-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6311-129">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f6311-129">Remarks</span></span>  

 <span data-ttu-id="f6311-130">Если узел реализует абстракцию завершения ввода-вывода, среда CLR делает запросы ввода-вывода через узел с помощью методов [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f6311-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="f6311-131">Затем узел вызывает метод, `OnComplete` чтобы уведомить среду выполнения о результатах таких запросов.</span><span class="sxs-lookup"><span data-stu-id="f6311-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6311-132">Требования</span><span class="sxs-lookup"><span data-stu-id="f6311-132">Requirements</span></span>  

 <span data-ttu-id="f6311-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6311-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6311-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f6311-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6311-135">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6311-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6311-136">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6311-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6311-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f6311-137">See also</span></span>

- [<span data-ttu-id="f6311-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f6311-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="f6311-139">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f6311-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="f6311-140">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="f6311-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
