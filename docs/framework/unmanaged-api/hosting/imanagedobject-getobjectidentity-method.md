---
title: Метод IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
ms.openlocfilehash: fc74b84bccceb1772bf3642e51ec88c562ce5dce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730722"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="6b077-102">Метод IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="6b077-102">IManagedObject::GetObjectIdentity Method</span></span>

<span data-ttu-id="6b077-103">Возвращает удостоверение этого управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="6b077-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b077-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b077-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b077-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b077-105">Parameters</span></span>  

 `pBSTRGUID`  
 <span data-ttu-id="6b077-106">заполняет Указатель на идентификатор GUID процесса, в котором находится объект.</span><span class="sxs-lookup"><span data-stu-id="6b077-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="6b077-107">заполняет Указатель на идентификатор домена приложения объекта.</span><span class="sxs-lookup"><span data-stu-id="6b077-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="6b077-108">заполняет Указатель на индекс объекта в классической таблице v-таблицы COM.</span><span class="sxs-lookup"><span data-stu-id="6b077-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b077-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6b077-109">Remarks</span></span>  

 <span data-ttu-id="6b077-110">Удостоверение управляемого объекта включает идентификатор GUID процесса, идентификатор домена приложения и индекс объекта в классической таблице v-таблицы COM.</span><span class="sxs-lookup"><span data-stu-id="6b077-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b077-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6b077-111">Requirements</span></span>  

 <span data-ttu-id="6b077-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b077-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b077-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6b077-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b077-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b077-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b077-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b077-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b077-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6b077-116">See also</span></span>

- [<span data-ttu-id="6b077-117">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="6b077-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
