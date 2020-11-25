---
title: Метод IHostMemoryManager::NeedsVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
ms.openlocfilehash: 74fbb2f162fbb68871f1bb4e1a1de32f5f913cd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731323"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="a317c-102">Метод IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="a317c-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>

<span data-ttu-id="a317c-103">Уведомляет узел о том, что среда CLR будет пытаться использовать указанную память.</span><span class="sxs-lookup"><span data-stu-id="a317c-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a317c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a317c-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a317c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a317c-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="a317c-106">окне Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="a317c-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="a317c-107">окне Размер памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="a317c-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a317c-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a317c-108">Remarks</span></span>  

 <span data-ttu-id="a317c-109">`NeedsVirtualAddressSpace`Метод является методом обратного вызова и должен быть реализован модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="a317c-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="a317c-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a317c-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="a317c-111">Если узел не хочет, чтобы среда CLR использовала указанную память, она может вернуть E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a317c-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a317c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a317c-112">Requirements</span></span>  

 <span data-ttu-id="a317c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a317c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a317c-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a317c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a317c-115">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a317c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a317c-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a317c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a317c-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a317c-117">See also</span></span>

- [<span data-ttu-id="a317c-118">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a317c-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
