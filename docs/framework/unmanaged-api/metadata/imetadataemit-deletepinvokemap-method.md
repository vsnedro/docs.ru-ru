---
title: Метод IMetaDataEmit::DeletePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 6fc6cf9b7333dd4caad3c5a4b081fecb060c8f86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722093"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="345e0-102">Метод IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="345e0-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="345e0-103">Уничтожает метаданные сопоставления PInvoke для объекта, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="345e0-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="345e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="345e0-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="345e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="345e0-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="345e0-106">окне `mdFieldDef` Токен или `mdMethodDef` , представляющий объект, для которого необходимо удалить метаданные сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="345e0-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="345e0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="345e0-107">Requirements</span></span>  

 <span data-ttu-id="345e0-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="345e0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="345e0-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="345e0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="345e0-110">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="345e0-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="345e0-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="345e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="345e0-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="345e0-112">See also</span></span>

- [<span data-ttu-id="345e0-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="345e0-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="345e0-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="345e0-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
