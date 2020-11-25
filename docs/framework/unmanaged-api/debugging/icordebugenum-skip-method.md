---
title: Метод ICorDebugEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: ae88336b9640b68b97522d252b3e8334c20ed9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705869"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="1ae59-102">Метод ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="1ae59-102">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="1ae59-103">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="1ae59-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae59-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ae59-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ae59-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ae59-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="1ae59-106">окне Число элементов, по которым перемещается курсор.</span><span class="sxs-lookup"><span data-stu-id="1ae59-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae59-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1ae59-107">Requirements</span></span>  

 <span data-ttu-id="1ae59-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ae59-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae59-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ae59-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ae59-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ae59-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ae59-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae59-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae59-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ae59-112">See also</span></span>

- [<span data-ttu-id="1ae59-113">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="1ae59-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
