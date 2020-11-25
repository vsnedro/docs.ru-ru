---
title: Метод IHostTaskManager::Sleep
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: 372b15a565f8a7484c1c42c387098a38f7bbf428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702060"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="30da3-102">Метод IHostTaskManager::Sleep</span><span class="sxs-lookup"><span data-stu-id="30da3-102">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="30da3-103">Уведомляет узел о том, что текущая задача переходит в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="30da3-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30da3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30da3-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30da3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30da3-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="30da3-106">окне Интервал времени в миллисекундах, в течение которого поток будет в спящем режиме.</span><span class="sxs-lookup"><span data-stu-id="30da3-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="30da3-107">окне Одно из значений перечисления [WAIT_OPTION](wait-option-enumeration.md) , указывающее, какое действие должно предпринять узел при блокировке этого действия.</span><span class="sxs-lookup"><span data-stu-id="30da3-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30da3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="30da3-108">Return Value</span></span>  
  
|<span data-ttu-id="30da3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30da3-109">HRESULT</span></span>|<span data-ttu-id="30da3-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="30da3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30da3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="30da3-111">S_OK</span></span>|<span data-ttu-id="30da3-112">`Sleep` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="30da3-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="30da3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30da3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30da3-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="30da3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30da3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30da3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30da3-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="30da3-116">The call timed out.</span></span>|  
|<span data-ttu-id="30da3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30da3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30da3-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="30da3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30da3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30da3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30da3-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="30da3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30da3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30da3-121">E_FAIL</span></span>|<span data-ttu-id="30da3-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="30da3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30da3-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="30da3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30da3-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30da3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30da3-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="30da3-125">Remarks</span></span>  

 <span data-ttu-id="30da3-126">Среда CLR обычно вызывает `IHostTaskManager::Sleep` метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> , когда вызывается из пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="30da3-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30da3-127">Требования</span><span class="sxs-lookup"><span data-stu-id="30da3-127">Requirements</span></span>  

 <span data-ttu-id="30da3-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30da3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30da3-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="30da3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30da3-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30da3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30da3-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30da3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30da3-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="30da3-132">See also</span></span>

- [<span data-ttu-id="30da3-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="30da3-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="30da3-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="30da3-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="30da3-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="30da3-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="30da3-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="30da3-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
