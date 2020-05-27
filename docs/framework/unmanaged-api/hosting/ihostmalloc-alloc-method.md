---
title: Метод IHostMAlloc::Alloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: 6f58e2290afa166d48306c0bbb50edd1df36888b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804649"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="f8733-102">Метод IHostMAlloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="f8733-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="f8733-103">Запрашивает, что узел выделяет указанный объем памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="f8733-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8733-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8733-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8733-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8733-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="f8733-106">окне Размер (в байтах) текущего запроса на выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="f8733-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="f8733-107">окне Одно из значений [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) , указывающее влияние сбоя выделения.</span><span class="sxs-lookup"><span data-stu-id="f8733-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="f8733-108">заполняет Указатель на выделенную память или значение null, если не удалось завершить запрос.</span><span class="sxs-lookup"><span data-stu-id="f8733-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8733-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f8733-109">Return Value</span></span>  
  
|<span data-ttu-id="f8733-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8733-110">HRESULT</span></span>|<span data-ttu-id="f8733-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f8733-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8733-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8733-112">S_OK</span></span>|<span data-ttu-id="f8733-113">`Alloc`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f8733-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="f8733-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8733-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8733-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f8733-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8733-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8733-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8733-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f8733-117">The call timed out.</span></span>|  
|<span data-ttu-id="f8733-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8733-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8733-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f8733-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8733-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8733-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8733-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f8733-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8733-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8733-122">E_FAIL</span></span>|<span data-ttu-id="f8733-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f8733-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8733-124">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f8733-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8733-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f8733-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f8733-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f8733-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f8733-127">Недостаточно памяти для завершения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="f8733-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8733-128">Замечания</span><span class="sxs-lookup"><span data-stu-id="f8733-128">Remarks</span></span>  
 <span data-ttu-id="f8733-129">Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляр, вызывая метод [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f8733-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8733-130">Требования</span><span class="sxs-lookup"><span data-stu-id="f8733-130">Requirements</span></span>  
 <span data-ttu-id="f8733-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8733-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8733-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f8733-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8733-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f8733-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8733-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8733-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8733-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f8733-135">See also</span></span>

- [<span data-ttu-id="f8733-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="f8733-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="f8733-137">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="f8733-137">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
