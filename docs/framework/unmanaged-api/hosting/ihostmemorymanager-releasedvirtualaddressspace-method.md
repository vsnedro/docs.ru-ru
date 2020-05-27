---
title: Метод IHostMemoryManager::ReleasedVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
ms.openlocfilehash: 4a246fb95ab5b4a7f187aa660f20e590c63ddff2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804458"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="71db1-102">Метод IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="71db1-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="71db1-103">Уведомляет узел о том, что среда CLR завершила работу с заданной памятью.</span><span class="sxs-lookup"><span data-stu-id="71db1-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71db1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71db1-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71db1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71db1-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="71db1-106">окне Указатель на начальный адрес памяти для освобождения.</span><span class="sxs-lookup"><span data-stu-id="71db1-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71db1-107">Замечания</span><span class="sxs-lookup"><span data-stu-id="71db1-107">Remarks</span></span>  
 <span data-ttu-id="71db1-108">`ReleasedVirtualAddressSpace`Метод является методом обратного вызова и должен быть реализован модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="71db1-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="71db1-109">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="71db1-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71db1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="71db1-110">Requirements</span></span>  
 <span data-ttu-id="71db1-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71db1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71db1-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71db1-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71db1-113">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71db1-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71db1-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71db1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71db1-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="71db1-115">See also</span></span>

- [<span data-ttu-id="71db1-116">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="71db1-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
