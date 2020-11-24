---
title: Метод ICorPublishEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: 888cc40c194cb86b0f898f5556ea14b8897e08c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693311"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="ec465-102">Метод ICorPublishEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="ec465-102">ICorPublishEnum::Skip Method</span></span>

<span data-ttu-id="ec465-103">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="ec465-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec465-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec465-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec465-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec465-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="ec465-106">окне Число элементов, по которым перемещается курсор.</span><span class="sxs-lookup"><span data-stu-id="ec465-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec465-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ec465-107">Requirements</span></span>  

 <span data-ttu-id="ec465-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec465-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec465-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="ec465-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ec465-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec465-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec465-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec465-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec465-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec465-112">See also</span></span>

- [<span data-ttu-id="ec465-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="ec465-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
