---
title: Метод IHostMAlloc::DebugAlloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 3f85e7c7fd54079ddce37f739a3a7bc0fa830d31
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493296"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="ff362-102">Метод IHostMAlloc::DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="ff362-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="ff362-103">Запрашивает, что узел выделяет указанный объем памяти из кучи, и дополнительно следит за местом выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="ff362-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff362-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff362-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff362-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff362-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="ff362-106">окне Размер (в байтах) текущего запроса на выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="ff362-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="ff362-107">окне Одно из значений [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) , указывающее влияние сбоя выделения.</span><span class="sxs-lookup"><span data-stu-id="ff362-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="ff362-108">окне Файл исходного кода отлаживаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="ff362-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="ff362-109">окне Номер строки, в `pszFileName` которой было запрошено выделение.</span><span class="sxs-lookup"><span data-stu-id="ff362-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="ff362-110">заполняет Указатель на выделенную память или значение null, если не удалось завершить запрос.</span><span class="sxs-lookup"><span data-stu-id="ff362-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff362-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff362-111">Return Value</span></span>  
  
|<span data-ttu-id="ff362-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff362-112">HRESULT</span></span>|<span data-ttu-id="ff362-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ff362-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff362-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff362-114">S_OK</span></span>|<span data-ttu-id="ff362-115">`DebugAlloc`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ff362-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="ff362-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ff362-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff362-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ff362-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ff362-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ff362-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ff362-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ff362-119">The call timed out.</span></span>|  
|<span data-ttu-id="ff362-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff362-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ff362-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ff362-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ff362-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ff362-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ff362-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ff362-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ff362-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff362-124">E_FAIL</span></span>|<span data-ttu-id="ff362-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ff362-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ff362-126">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ff362-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ff362-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ff362-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ff362-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ff362-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ff362-129">Недостаточно памяти для завершения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="ff362-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff362-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff362-130">Remarks</span></span>  
 <span data-ttu-id="ff362-131">Среда CLR получает указатель интерфейса на экземпляр [IHostMalloc](ihostmalloc-interface.md) , вызывая метод [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ff362-131">The CLR gets an interface pointer to an [IHostMalloc](ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="ff362-132">`DebugAlloc`позволяет среде выполнения получать сведения о файле кода для использования во время отладки.</span><span class="sxs-lookup"><span data-stu-id="ff362-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff362-133">Требования</span><span class="sxs-lookup"><span data-stu-id="ff362-133">Requirements</span></span>  
 <span data-ttu-id="ff362-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff362-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff362-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ff362-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff362-136">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ff362-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff362-137">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff362-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff362-138">См. также</span><span class="sxs-lookup"><span data-stu-id="ff362-138">See also</span></span>

- [<span data-ttu-id="ff362-139">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="ff362-139">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="ff362-140">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="ff362-140">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
