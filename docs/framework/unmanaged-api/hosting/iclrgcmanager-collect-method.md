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
ms.openlocfilehash: aa906e314c408b7653e611b07d7ad21d4519b715
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616987"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="e22fa-102">Метод ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="e22fa-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="e22fa-103">Вызывает принудительную сборку мусора для указанного поколения.</span><span class="sxs-lookup"><span data-stu-id="e22fa-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e22fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e22fa-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e22fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e22fa-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e22fa-106">окне Поколение, которое необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="e22fa-106">[in] The generation to collect.</span></span> <span data-ttu-id="e22fa-107">Значение-1 вызывает сбор всех поколений.</span><span class="sxs-lookup"><span data-stu-id="e22fa-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e22fa-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e22fa-108">Return Value</span></span>  
  
|<span data-ttu-id="e22fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e22fa-109">HRESULT</span></span>|<span data-ttu-id="e22fa-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e22fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e22fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e22fa-111">S_OK</span></span>|<span data-ttu-id="e22fa-112">`Collect`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="e22fa-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="e22fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e22fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e22fa-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e22fa-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e22fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e22fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e22fa-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="e22fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="e22fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e22fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e22fa-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="e22fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e22fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e22fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e22fa-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="e22fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e22fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e22fa-121">E_FAIL</span></span>|<span data-ttu-id="e22fa-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="e22fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e22fa-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e22fa-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e22fa-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e22fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e22fa-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e22fa-125">Remarks</span></span>  
 <span data-ttu-id="e22fa-126">`Collect`Метод заставляет сборщик мусора среды CLR выполнить сбор данных независимо от его текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="e22fa-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e22fa-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e22fa-127">Requirements</span></span>  
 <span data-ttu-id="e22fa-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e22fa-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e22fa-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e22fa-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e22fa-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e22fa-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e22fa-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e22fa-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22fa-132">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e22fa-132">See also</span></span>

- [<span data-ttu-id="e22fa-133">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="e22fa-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="e22fa-134">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="e22fa-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="e22fa-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e22fa-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e22fa-136">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="e22fa-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="e22fa-137">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e22fa-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="e22fa-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e22fa-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e22fa-139">Размещение</span><span class="sxs-lookup"><span data-stu-id="e22fa-139">Hosting</span></span>](index.md)
