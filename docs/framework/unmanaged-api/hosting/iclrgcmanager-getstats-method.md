---
title: Метод ICLRGCManager::GetStats
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
ms.openlocfilehash: 8622920a81f4b469361ffa879f7a4eeda697cab9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504229"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="81336-102">Метод ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="81336-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="81336-103">Возвращает набор текущих статистических данных о системе сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="81336-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81336-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81336-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81336-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81336-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="81336-106">[вход, выход] Экземпляр [COR_GC_STATS](cor-gc-stats-structure.md) , содержащий запрошенную статистику.</span><span class="sxs-lookup"><span data-stu-id="81336-106">[in, out] A [COR_GC_STATS](cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81336-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81336-107">Return Value</span></span>  
  
|<span data-ttu-id="81336-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81336-108">HRESULT</span></span>|<span data-ttu-id="81336-109">Описание</span><span class="sxs-lookup"><span data-stu-id="81336-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81336-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="81336-110">S_OK</span></span>|<span data-ttu-id="81336-111">`GetStats`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="81336-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="81336-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81336-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81336-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="81336-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81336-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81336-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81336-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="81336-115">The call timed out.</span></span>|  
|<span data-ttu-id="81336-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81336-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81336-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="81336-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81336-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81336-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81336-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="81336-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81336-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81336-120">E_FAIL</span></span>|<span data-ttu-id="81336-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="81336-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81336-122">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="81336-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81336-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81336-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81336-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="81336-124">Remarks</span></span>  
 <span data-ttu-id="81336-125">Среда CLR вычисляет и возвращает только те статистические данные, которые указаны в `Flags` поле `pStats` .</span><span class="sxs-lookup"><span data-stu-id="81336-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="81336-126">Задайте в `Flags` поле одно или несколько значений перечисления [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) , чтобы указать, какие статистические данные должны быть заданы в структуре [COR_GC_STATS](cor-gc-stats-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="81336-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="81336-127">Пример использования таков:</span><span class="sxs-lookup"><span data-stu-id="81336-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="81336-128">Требования</span><span class="sxs-lookup"><span data-stu-id="81336-128">Requirements</span></span>  
 <span data-ttu-id="81336-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81336-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81336-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81336-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81336-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81336-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81336-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81336-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81336-133">См. также</span><span class="sxs-lookup"><span data-stu-id="81336-133">See also</span></span>

- [<span data-ttu-id="81336-134">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="81336-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="81336-135">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="81336-135">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="81336-136">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="81336-136">COR_GC_STAT_TYPES Enumeration</span></span>](cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="81336-137">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="81336-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="81336-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="81336-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="81336-139">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="81336-139">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="81336-140">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="81336-140">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="81336-141">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="81336-141">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="81336-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="81336-142">Hosting</span></span>](index.md)
