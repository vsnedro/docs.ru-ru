---
title: Метод IHostCrst::TryEnter
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
ms.openlocfilehash: 02f36068f12bf0a40e5f0ac477803abfb84c72a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729542"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="89a2b-102">Метод IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="89a2b-102">IHostCrst::TryEnter Method</span></span>

<span data-ttu-id="89a2b-103">Пытается ввести критическую секцию, представленную текущим экземпляром [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="89a2b-103">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89a2b-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89a2b-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="89a2b-106">окне Одно из значений [WAIT_OPTION](wait-option-enumeration.md) , указывающее, какое действие должно предпринять узел при блокировке операции.</span><span class="sxs-lookup"><span data-stu-id="89a2b-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="89a2b-107">[out] `true` значение, если можно указать критический раздел; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="89a2b-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89a2b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89a2b-108">Return Value</span></span>  
  
|<span data-ttu-id="89a2b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89a2b-109">HRESULT</span></span>|<span data-ttu-id="89a2b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="89a2b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89a2b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="89a2b-111">S_OK</span></span>|<span data-ttu-id="89a2b-112">`TryEnter` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="89a2b-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="89a2b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89a2b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89a2b-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="89a2b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89a2b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89a2b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89a2b-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="89a2b-116">The call timed out.</span></span>|  
|<span data-ttu-id="89a2b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89a2b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89a2b-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="89a2b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89a2b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89a2b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89a2b-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="89a2b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89a2b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89a2b-121">E_FAIL</span></span>|<span data-ttu-id="89a2b-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="89a2b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89a2b-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="89a2b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89a2b-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89a2b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89a2b-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="89a2b-125">Remarks</span></span>  

 <span data-ttu-id="89a2b-126">`TryEnter` Возвращает значение немедленно и указывает, вошел ли вызывающий поток в критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="89a2b-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="89a2b-127">Этот метод отражает функцию Wind32 `TryEnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="89a2b-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a2b-128">Требования</span><span class="sxs-lookup"><span data-stu-id="89a2b-128">Requirements</span></span>  

 <span data-ttu-id="89a2b-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a2b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a2b-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="89a2b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89a2b-131">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89a2b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89a2b-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a2b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a2b-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89a2b-133">See also</span></span>

- [<span data-ttu-id="89a2b-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="89a2b-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="89a2b-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="89a2b-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="89a2b-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="89a2b-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
