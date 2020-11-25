---
title: Метод IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: be006afaf5966aa4e6d11c73b92004d676c97c7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731271"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="0eb21-102">Метод IHostMemoryManager::VirtualFree</span><span class="sxs-lookup"><span data-stu-id="0eb21-102">IHostMemoryManager::VirtualFree Method</span></span>

<span data-ttu-id="0eb21-103">Служит логической оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="0eb21-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="0eb21-104">Реализация в Win32 `VirtualFree` выпусков, снятие фиксаций, освобождение и отменяет фиксацию области страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="0eb21-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb21-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0eb21-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eb21-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0eb21-106">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="0eb21-107">окне Указатель на базовый адрес страниц виртуальной памяти, которые должны быть освобождены.</span><span class="sxs-lookup"><span data-stu-id="0eb21-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="0eb21-108">окне Размер (в байтах) области, которая должна быть освобождена.</span><span class="sxs-lookup"><span data-stu-id="0eb21-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="0eb21-109">окне Тип операции освобождения.</span><span class="sxs-lookup"><span data-stu-id="0eb21-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eb21-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0eb21-110">Return Value</span></span>  
  
|<span data-ttu-id="0eb21-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0eb21-111">HRESULT</span></span>|<span data-ttu-id="0eb21-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="0eb21-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0eb21-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0eb21-113">S_OK</span></span>|<span data-ttu-id="0eb21-114">`VirtualFree` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0eb21-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="0eb21-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0eb21-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0eb21-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0eb21-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0eb21-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0eb21-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0eb21-118">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0eb21-118">The call timed out.</span></span>|  
|<span data-ttu-id="0eb21-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0eb21-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0eb21-120">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0eb21-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0eb21-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0eb21-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0eb21-122">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0eb21-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0eb21-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0eb21-123">E_FAIL</span></span>|<span data-ttu-id="0eb21-124">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0eb21-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0eb21-125">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0eb21-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0eb21-126">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0eb21-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0eb21-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="0eb21-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="0eb21-128">Предпринята попытка освободить память, которая не была выделена через узел.</span><span class="sxs-lookup"><span data-stu-id="0eb21-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eb21-129">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0eb21-129">Remarks</span></span>  

 <span data-ttu-id="0eb21-130">`VirtualFree` Освобождает страницы виртуальной памяти, связанные с `lpAddress` параметром, с помощью предыдущего вызова функции [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0eb21-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="0eb21-131">Пытается освободить память, которая не была выделена с помощью узла, должна возвращать HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="0eb21-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="0eb21-132">Семантика идентична реализации Win32 `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="0eb21-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="0eb21-133">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="0eb21-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eb21-134">Требования</span><span class="sxs-lookup"><span data-stu-id="0eb21-134">Requirements</span></span>  

 <span data-ttu-id="0eb21-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eb21-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eb21-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0eb21-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0eb21-137">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0eb21-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0eb21-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eb21-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb21-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0eb21-139">See also</span></span>

- [<span data-ttu-id="0eb21-140">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0eb21-140">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="0eb21-141">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="0eb21-141">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
