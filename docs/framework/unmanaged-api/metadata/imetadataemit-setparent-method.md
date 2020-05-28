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
ms.openlocfilehash: da82950ea1a0da81c77d173be9ab45dcb3001bfe
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007836"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="f9d21-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="f9d21-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="f9d21-103">Устанавливает, что указанный элемент, как определено в предыдущем вызове [IMetaDataEmit::D ефинемемберреф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), является членом указанного типа, как определено в предыдущем вызове [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="f9d21-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9d21-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9d21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9d21-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="f9d21-106">окне `mdMemberRef`Токен для получения нового родителя.</span><span class="sxs-lookup"><span data-stu-id="f9d21-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="f9d21-107">окне `mdToken`Для нового родителя.</span><span class="sxs-lookup"><span data-stu-id="f9d21-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9d21-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f9d21-108">Requirements</span></span>  
 <span data-ttu-id="f9d21-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9d21-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9d21-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f9d21-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9d21-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f9d21-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9d21-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9d21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d21-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f9d21-113">See also</span></span>

- [<span data-ttu-id="f9d21-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f9d21-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f9d21-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f9d21-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
