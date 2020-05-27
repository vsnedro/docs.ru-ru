---
title: Метод IHostIoCompletionManager::CloseIoCompletionPort
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: 5e2e49b4c993e127a31b54d40f721e0714198780
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804778"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="7f160-102">Метод IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="7f160-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="7f160-103">Запрашивает, что узел закрывает порт, Открытый с помощью предыдущего вызова [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="7f160-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f160-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f160-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f160-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f160-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="7f160-106">окне Маркер порта, который необходимо закрыть.</span><span class="sxs-lookup"><span data-stu-id="7f160-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f160-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7f160-107">Return Value</span></span>  
  
|<span data-ttu-id="7f160-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f160-108">HRESULT</span></span>|<span data-ttu-id="7f160-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7f160-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f160-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f160-110">S_OK</span></span>|<span data-ttu-id="7f160-111">`CloseIoCompletionPort`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="7f160-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="7f160-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f160-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f160-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7f160-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f160-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f160-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f160-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="7f160-115">The call timed out.</span></span>|  
|<span data-ttu-id="7f160-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f160-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f160-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="7f160-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f160-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f160-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f160-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="7f160-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f160-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f160-120">E_FAIL</span></span>|<span data-ttu-id="7f160-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7f160-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f160-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7f160-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f160-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7f160-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7f160-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7f160-124">E_INVALIDARG</span></span>|<span data-ttu-id="7f160-125">Передан недопустимый маркер порта.</span><span class="sxs-lookup"><span data-stu-id="7f160-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f160-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="7f160-126">Remarks</span></span>  
 <span data-ttu-id="7f160-127">`hPort`должен быть маркером для порта, созданного предыдущим вызовом метода `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="7f160-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f160-128">Требования</span><span class="sxs-lookup"><span data-stu-id="7f160-128">Requirements</span></span>  
 <span data-ttu-id="7f160-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f160-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f160-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7f160-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f160-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7f160-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f160-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f160-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f160-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7f160-133">See also</span></span>

- [<span data-ttu-id="7f160-134">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="7f160-134">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="7f160-135">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="7f160-135">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
