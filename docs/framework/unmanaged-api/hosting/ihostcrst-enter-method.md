---
title: Метод IHostCrst::Enter
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: a5c2646d7c9dbf8a7aea4a7fb9bd0a6b8c1d5d66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680557"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="f2183-102">Метод IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="f2183-102">IHostCrst::Enter Method</span></span>

<span data-ttu-id="f2183-103">Вводит критическую секцию, представленную текущим экземпляром [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f2183-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2183-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2183-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2183-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2183-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="f2183-106">окне Одно из значений [WAIT_OPTION](wait-option-enumeration.md) , указывающее, какое действие должно предпринять узел при блокировке операции.</span><span class="sxs-lookup"><span data-stu-id="f2183-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2183-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2183-107">Return Value</span></span>  
  
|<span data-ttu-id="f2183-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2183-108">HRESULT</span></span>|<span data-ttu-id="f2183-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="f2183-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2183-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2183-110">S_OK</span></span>|<span data-ttu-id="f2183-111">`Enter` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f2183-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="f2183-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2183-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2183-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f2183-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2183-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2183-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2183-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f2183-115">The call timed out.</span></span>|  
|<span data-ttu-id="f2183-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2183-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2183-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f2183-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2183-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2183-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2183-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f2183-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2183-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2183-120">E_FAIL</span></span>|<span data-ttu-id="f2183-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f2183-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2183-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f2183-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2183-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f2183-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2183-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f2183-124">Remarks</span></span>  

 <span data-ttu-id="f2183-125">`Enter` отражает функцию Win32 `EnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="f2183-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2183-126">Этот метод не возвращает значение до тех пор, пока не будет указан критический раздел.</span><span class="sxs-lookup"><span data-stu-id="f2183-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2183-127">Требования</span><span class="sxs-lookup"><span data-stu-id="f2183-127">Requirements</span></span>  

 <span data-ttu-id="f2183-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2183-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2183-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f2183-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2183-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2183-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2183-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2183-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2183-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2183-132">See also</span></span>

- [<span data-ttu-id="f2183-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f2183-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f2183-134">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="f2183-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="f2183-135">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f2183-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
