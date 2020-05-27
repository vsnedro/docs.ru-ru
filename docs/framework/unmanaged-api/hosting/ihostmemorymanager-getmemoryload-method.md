---
title: Метод IHostMemoryManager::GetMemoryLoad
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 73d9ae865b2c971a4defcacf5bd6505836c74e02
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804507"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="d55ef-102">Метод IHostMemoryManager::GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="d55ef-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="d55ef-103">Возвращает объем физической памяти, используемой в данный момент, и, следовательно, недоступен, сообщаемый узлом.</span><span class="sxs-lookup"><span data-stu-id="d55ef-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d55ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d55ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d55ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d55ef-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="d55ef-106">заполняет Указатель на Приблизительный процент общего объема физической памяти, который используется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="d55ef-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="d55ef-107">заполняет Указатель на число байтов, доступных для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d55ef-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d55ef-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d55ef-108">Return Value</span></span>  
  
|<span data-ttu-id="d55ef-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d55ef-109">HRESULT</span></span>|<span data-ttu-id="d55ef-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d55ef-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d55ef-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d55ef-111">S_OK</span></span>|<span data-ttu-id="d55ef-112">`GetMemoryLoad`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d55ef-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="d55ef-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d55ef-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d55ef-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d55ef-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d55ef-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d55ef-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d55ef-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d55ef-116">The call timed out.</span></span>|  
|<span data-ttu-id="d55ef-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d55ef-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d55ef-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d55ef-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d55ef-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d55ef-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d55ef-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d55ef-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d55ef-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d55ef-121">E_FAIL</span></span>|<span data-ttu-id="d55ef-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d55ef-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d55ef-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d55ef-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d55ef-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d55ef-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d55ef-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="d55ef-125">Remarks</span></span>  
 <span data-ttu-id="d55ef-126">`GetMemoryLoad`заключает в оболочку `GlobalMemoryStatus` функцию Win32.</span><span class="sxs-lookup"><span data-stu-id="d55ef-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="d55ef-127">Значение `pMemoryLoad` является эквивалентом `dwMemoryLoad` поля в `MEMORYSTATUS` структуре, возвращаемой из `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="d55ef-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="d55ef-128">Среда выполнения использует возвращаемое значение в качестве эвристики для сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="d55ef-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="d55ef-129">Например, если основное приложение сообщает о том, что используется большая часть памяти, сборщик мусора может выбрать сбор данных из нескольких поколений, чтобы увеличить объем памяти, который потенциально может стать доступным.</span><span class="sxs-lookup"><span data-stu-id="d55ef-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d55ef-130">Требования</span><span class="sxs-lookup"><span data-stu-id="d55ef-130">Requirements</span></span>  
 <span data-ttu-id="d55ef-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d55ef-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d55ef-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d55ef-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d55ef-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d55ef-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d55ef-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d55ef-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55ef-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d55ef-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="d55ef-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="d55ef-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
