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
ms.openlocfilehash: 79af7b5679598ffa82471dcb69adabc2394b13fa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009305"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="d1df6-102">Метод IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="d1df6-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="d1df6-103">Уничтожает метаданные сопоставления PInvoke для объекта, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="d1df6-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1df6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1df6-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1df6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1df6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d1df6-106">окне `mdFieldDef`Токен или `mdMethodDef` , представляющий объект, для которого необходимо удалить метаданные сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="d1df6-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1df6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d1df6-107">Requirements</span></span>  
 <span data-ttu-id="d1df6-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1df6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1df6-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d1df6-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1df6-110">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d1df6-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1df6-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1df6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1df6-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d1df6-112">See also</span></span>

- [<span data-ttu-id="d1df6-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d1df6-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d1df6-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d1df6-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
