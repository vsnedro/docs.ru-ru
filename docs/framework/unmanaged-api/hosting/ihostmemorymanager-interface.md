---
title: Интерфейс IHostMemoryManager
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: 4e7e76a4a3ab291ee97ad0912e3d6224cdf96fba
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804488"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="79e4f-102">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="79e4f-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="79e4f-103">Предоставляет методы, позволяющие среде CLR выполнять запросы к виртуальной памяти через основное приложение вместо использования стандартных функций виртуальной памяти Win32.</span><span class="sxs-lookup"><span data-stu-id="79e4f-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79e4f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="79e4f-104">Methods</span></span>  
  
|<span data-ttu-id="79e4f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="79e4f-105">Method</span></span>|<span data-ttu-id="79e4f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="79e4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79e4f-107">Метод AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="79e4f-107">AcquiredVirtualAddressSpace Method</span></span>](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="79e4f-108">Уведомляет узел о том, что среда CLR получила указанную память из операционной системы.</span><span class="sxs-lookup"><span data-stu-id="79e4f-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="79e4f-109">Метод CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="79e4f-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="79e4f-110">Возвращает указатель интерфейса на экземпляр [IHostMAlloc](ihostmalloc-interface.md) , который используется для запроса выделения памяти из кучи, созданного узлом.</span><span class="sxs-lookup"><span data-stu-id="79e4f-110">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="79e4f-111">Метод GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="79e4f-111">GetMemoryLoad Method</span></span>](ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="79e4f-112">Возвращает объем используемой в данный момент физической памяти, сообщаемой узлом.</span><span class="sxs-lookup"><span data-stu-id="79e4f-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="79e4f-113">Метод NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="79e4f-113">NeedsVirtualAddressSpace Method</span></span>](ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="79e4f-114">Уведомляет узел о том, что среда CLR будет пытаться использовать указанную память.</span><span class="sxs-lookup"><span data-stu-id="79e4f-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="79e4f-115">Метод RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="79e4f-115">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="79e4f-116">Регистрирует указатель на функцию обратного вызова, которая вызывается хостом для уведомления среды CLR о текущей загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="79e4f-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="79e4f-117">Метод ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="79e4f-117">ReleasedVirtualAddressSpace Method</span></span>](ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="79e4f-118">Уведомляет узел о том, что среда CLR завершила работу с заданной памятью.</span><span class="sxs-lookup"><span data-stu-id="79e4f-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="79e4f-119">Метод VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="79e4f-119">VirtualAlloc Method</span></span>](ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="79e4f-120">Служит логической оболочкой для соответствующей функции Win32, которая резервирует или фиксирует область страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="79e4f-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="79e4f-121">Метод VirtualFree</span><span class="sxs-lookup"><span data-stu-id="79e4f-121">VirtualFree Method</span></span>](ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="79e4f-122">Служит логической оболочкой для соответствующей функции Win32, которая выдает, выдает или освобождает и отменяет выделение области страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="79e4f-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="79e4f-123">Метод VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="79e4f-123">VirtualProtect Method</span></span>](ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="79e4f-124">Служит логической оболочкой для соответствующей функции Win32, которая изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="79e4f-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="79e4f-125">Метод VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="79e4f-125">VirtualQuery Method</span></span>](ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="79e4f-126">Служит логической оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="79e4f-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79e4f-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="79e4f-127">Remarks</span></span>  
 <span data-ttu-id="79e4f-128">`IHostMemoryManager`также предоставляет методы для среды CLR для получения указателя, с помощью которого можно выполнять запросы к памяти в куче и получать уровень нехватки памяти в процессе, сообщаемый узлом.</span><span class="sxs-lookup"><span data-stu-id="79e4f-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79e4f-129">Требования</span><span class="sxs-lookup"><span data-stu-id="79e4f-129">Requirements</span></span>  
 <span data-ttu-id="79e4f-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79e4f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79e4f-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="79e4f-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79e4f-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="79e4f-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79e4f-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79e4f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e4f-134">См. также статью</span><span class="sxs-lookup"><span data-stu-id="79e4f-134">See also</span></span>

- [<span data-ttu-id="79e4f-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="79e4f-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="79e4f-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="79e4f-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
