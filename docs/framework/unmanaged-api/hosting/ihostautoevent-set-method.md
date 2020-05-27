---
title: Метод IHostAutoEvent::Set
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: 55fd858927743b097e5e842c0897a16d36b76733
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804988"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="75544-102">Метод IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="75544-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="75544-103">Устанавливает для текущего экземпляра [ихостаутоевент](ihostautoevent-interface.md) сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="75544-103">Sets the current [IHostAutoEvent](ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75544-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75544-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="75544-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="75544-105">Return Value</span></span>  
  
|<span data-ttu-id="75544-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75544-106">HRESULT</span></span>|<span data-ttu-id="75544-107">Описание</span><span class="sxs-lookup"><span data-stu-id="75544-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75544-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="75544-108">S_OK</span></span>|<span data-ttu-id="75544-109">`Set`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="75544-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="75544-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75544-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75544-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="75544-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="75544-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="75544-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="75544-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="75544-113">The call timed out.</span></span>|  
|<span data-ttu-id="75544-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="75544-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="75544-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="75544-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="75544-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="75544-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="75544-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="75544-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="75544-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75544-118">E_FAIL</span></span>|<span data-ttu-id="75544-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="75544-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="75544-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="75544-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="75544-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="75544-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75544-122">Требования</span><span class="sxs-lookup"><span data-stu-id="75544-122">Requirements</span></span>  
 <span data-ttu-id="75544-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75544-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75544-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="75544-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75544-125">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="75544-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75544-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75544-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75544-127">См. также статью</span><span class="sxs-lookup"><span data-stu-id="75544-127">See also</span></span>

- [<span data-ttu-id="75544-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="75544-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="75544-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="75544-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="75544-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="75544-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="75544-131">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="75544-131">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
