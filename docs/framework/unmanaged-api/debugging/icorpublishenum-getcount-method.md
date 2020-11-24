---
title: Метод ICorPublishEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: a23d61da2913d8732c3860a44eb58ffadab48315
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677938"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="1e3e1-102">Метод ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="1e3e1-102">ICorPublishEnum::GetCount Method</span></span>

<span data-ttu-id="1e3e1-103">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e3e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e3e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e3e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e3e1-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="1e3e1-106">заполняет Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="1e3e1-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e3e1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1e3e1-107">Requirements</span></span>  

 <span data-ttu-id="1e3e1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e3e1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e3e1-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="1e3e1-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1e3e1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e3e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e3e1-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e3e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3e1-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1e3e1-112">See also</span></span>

- [<span data-ttu-id="1e3e1-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="1e3e1-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
