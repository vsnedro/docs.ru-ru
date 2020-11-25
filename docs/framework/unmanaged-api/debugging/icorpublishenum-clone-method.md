---
title: Метод ICorPublishEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 44ecba99999d04603477f411e68834548f6a7cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693558"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="7f11d-102">Метод ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="7f11d-102">ICorPublishEnum::Clone Method</span></span>

<span data-ttu-id="7f11d-103">Создает копию этого объекта [ICorPublishEnum](icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7f11d-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f11d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f11d-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f11d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f11d-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="7f11d-106">заполняет Указатель на адрес `ICorPublishEnum` объекта, который является копией этого `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="7f11d-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f11d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7f11d-107">Requirements</span></span>  

 <span data-ttu-id="7f11d-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f11d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f11d-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="7f11d-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7f11d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f11d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f11d-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f11d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f11d-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7f11d-112">See also</span></span>

- [<span data-ttu-id="7f11d-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="7f11d-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
