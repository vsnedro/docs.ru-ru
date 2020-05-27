---
title: Интерфейс IHostMalloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: 8f4e1cd7586df7d8e2a577d26f06eaed6b2c8bb7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804601"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="3797b-102">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="3797b-102">IHostMalloc Interface</span></span>
<span data-ttu-id="3797b-103">Предоставляет методы, позволяющие среде CLR запрашивать детализированные выделения из кучи через узел.</span><span class="sxs-lookup"><span data-stu-id="3797b-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3797b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3797b-104">Methods</span></span>  
  
|<span data-ttu-id="3797b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3797b-105">Method</span></span>|<span data-ttu-id="3797b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3797b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3797b-107">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="3797b-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="3797b-108">Запрашивает у узла выделение запрошенного объема памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="3797b-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="3797b-109">Метод DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="3797b-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="3797b-110">Запрашивает, что узел выделяет запрошенный объем памяти из кучи, и дополнительно следит за местом выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="3797b-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="3797b-111">Метод Free</span><span class="sxs-lookup"><span data-stu-id="3797b-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="3797b-112">Освобождает память, выделенную с помощью `Alloc` метода.</span><span class="sxs-lookup"><span data-stu-id="3797b-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3797b-113">Замечания</span><span class="sxs-lookup"><span data-stu-id="3797b-113">Remarks</span></span>  
 <span data-ttu-id="3797b-114">Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляр, вызывая метод [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3797b-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3797b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3797b-115">Requirements</span></span>  
 <span data-ttu-id="3797b-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3797b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3797b-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3797b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3797b-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3797b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3797b-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3797b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3797b-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3797b-120">See also</span></span>

- [<span data-ttu-id="3797b-121">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="3797b-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="3797b-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3797b-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
