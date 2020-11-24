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
ms.openlocfilehash: facfbb85645f444b010cb1fe1c34bbe94011ac50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680833"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="0e692-102">Метод IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="0e692-102">IHostAutoEvent::Set Method</span></span>

<span data-ttu-id="0e692-103">Устанавливает для текущего экземпляра [ихостаутоевент](ihostautoevent-interface.md) сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="0e692-103">Sets the current [IHostAutoEvent](ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e692-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e692-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0e692-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e692-105">Return Value</span></span>  
  
|<span data-ttu-id="0e692-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e692-106">HRESULT</span></span>|<span data-ttu-id="0e692-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0e692-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e692-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e692-108">S_OK</span></span>|<span data-ttu-id="0e692-109">`Set` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0e692-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="0e692-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e692-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e692-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0e692-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e692-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e692-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e692-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0e692-113">The call timed out.</span></span>|  
|<span data-ttu-id="0e692-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e692-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e692-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0e692-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e692-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e692-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e692-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0e692-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e692-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e692-118">E_FAIL</span></span>|<span data-ttu-id="0e692-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0e692-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e692-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0e692-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e692-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0e692-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e692-122">Требования</span><span class="sxs-lookup"><span data-stu-id="0e692-122">Requirements</span></span>  

 <span data-ttu-id="0e692-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e692-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e692-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e692-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e692-125">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e692-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e692-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e692-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e692-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e692-127">See also</span></span>

- [<span data-ttu-id="0e692-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0e692-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="0e692-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0e692-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="0e692-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0e692-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="0e692-131">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0e692-131">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
