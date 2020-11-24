---
title: Метод ICLRGCManager::Collect
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: 90ce4e888ddb3a10dd0dfd7e68463311db86742f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677769"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="10892-102">Метод ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="10892-102">ICLRGCManager::Collect Method</span></span>

<span data-ttu-id="10892-103">Вызывает принудительную сборку мусора для указанного поколения.</span><span class="sxs-lookup"><span data-stu-id="10892-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10892-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10892-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10892-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10892-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="10892-106">окне Поколение, которое необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="10892-106">[in] The generation to collect.</span></span> <span data-ttu-id="10892-107">Значение-1 вызывает сбор всех поколений.</span><span class="sxs-lookup"><span data-stu-id="10892-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10892-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10892-108">Return Value</span></span>  
  
|<span data-ttu-id="10892-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10892-109">HRESULT</span></span>|<span data-ttu-id="10892-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="10892-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10892-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="10892-111">S_OK</span></span>|<span data-ttu-id="10892-112">`Collect` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="10892-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="10892-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10892-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10892-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="10892-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10892-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10892-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10892-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="10892-116">The call timed out.</span></span>|  
|<span data-ttu-id="10892-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10892-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10892-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="10892-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10892-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10892-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10892-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="10892-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10892-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10892-121">E_FAIL</span></span>|<span data-ttu-id="10892-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="10892-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10892-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="10892-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10892-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10892-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10892-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="10892-125">Remarks</span></span>  

 <span data-ttu-id="10892-126">`Collect`Метод заставляет сборщик мусора среды CLR выполнить сбор данных независимо от его текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="10892-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10892-127">Требования</span><span class="sxs-lookup"><span data-stu-id="10892-127">Requirements</span></span>  

 <span data-ttu-id="10892-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10892-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10892-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="10892-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10892-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10892-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10892-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10892-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10892-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10892-132">See also</span></span>

- [<span data-ttu-id="10892-133">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="10892-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="10892-134">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="10892-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="10892-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="10892-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="10892-136">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="10892-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="10892-137">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="10892-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="10892-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="10892-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="10892-139">Размещение</span><span class="sxs-lookup"><span data-stu-id="10892-139">Hosting</span></span>](index.md)
