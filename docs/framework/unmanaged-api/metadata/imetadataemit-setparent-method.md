---
title: Метод IMetaDataEmit::SetParent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: d821413e67b36392d936499cd22f2e065f1556ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503852"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="8537f-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="8537f-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="8537f-103">Устанавливает, что указанный элемент, как определено в предыдущем вызове [IMetaDataEmit::D ефинемемберреф](imetadataemit-definememberref-method.md), является членом указанного типа, как определено в предыдущем вызове [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="8537f-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8537f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8537f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8537f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8537f-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="8537f-106">окне `mdMemberRef`Токен для получения нового родителя.</span><span class="sxs-lookup"><span data-stu-id="8537f-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="8537f-107">окне `mdToken`Для нового родителя.</span><span class="sxs-lookup"><span data-stu-id="8537f-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8537f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8537f-108">Requirements</span></span>  
 <span data-ttu-id="8537f-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8537f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8537f-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8537f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8537f-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8537f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8537f-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8537f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8537f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8537f-113">See also</span></span>

- [<span data-ttu-id="8537f-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8537f-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8537f-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8537f-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
