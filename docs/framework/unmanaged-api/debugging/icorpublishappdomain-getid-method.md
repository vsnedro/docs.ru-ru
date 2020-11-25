---
title: Метод ICorPublishAppDomain::GetID
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: ab331145a8147e8830cb9b158a1975bc748c7cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716867"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="8bca5-102">Метод ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="8bca5-102">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="8bca5-103">Возвращает уникальный идентификатор для этого [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8bca5-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bca5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bca5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bca5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bca5-105">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="8bca5-106">заполняет Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8bca5-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bca5-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8bca5-107">Remarks</span></span>  

 <span data-ttu-id="8bca5-108">Идентификатор уникален только в области содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="8bca5-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bca5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8bca5-109">Requirements</span></span>  

 <span data-ttu-id="8bca5-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bca5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bca5-111">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="8bca5-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8bca5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bca5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bca5-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bca5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bca5-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8bca5-114">See also</span></span>

- [<span data-ttu-id="8bca5-115">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="8bca5-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
