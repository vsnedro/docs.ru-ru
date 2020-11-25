---
title: Метод IAssemblyEnum::Clone
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::Clone
helpviewer_keywords:
- Clone method, IAssemblyEnum interface [.NET Framework fusion]
- IAssemblyEnum::Clone method [.NET Framework fusion]
ms.assetid: 0014bb66-590c-486c-9ade-f2133905cd99
topic_type:
- apiref
ms.openlocfilehash: e1eef43858e4f38888f9f31e3076b092fbdd5633
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719909"
---
# <a name="iassemblyenumclone-method"></a><span data-ttu-id="855ba-102">Метод IAssemblyEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="855ba-102">IAssemblyEnum::Clone Method</span></span>

<span data-ttu-id="855ba-103">Создает неполную копию этого объекта [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="855ba-103">Creates a shallow copy of this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="855ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="855ba-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="855ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="855ba-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="855ba-106">заполняет Указатель на копию.</span><span class="sxs-lookup"><span data-stu-id="855ba-106">[out] A pointer to the copy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="855ba-107">Требования</span><span class="sxs-lookup"><span data-stu-id="855ba-107">Requirements</span></span>  

 <span data-ttu-id="855ba-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="855ba-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="855ba-109">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="855ba-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="855ba-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="855ba-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855ba-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="855ba-111">See also</span></span>

- [<span data-ttu-id="855ba-112">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="855ba-112">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
