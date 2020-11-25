---
title: Метод IMetaDataEmit::DeleteFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 5989c45782b4f83ecfa285cb305080320abf6a3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700552"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="f7554-102">Метод IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="f7554-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="f7554-103">Уничтожает сигнатуру метаданных упаковки PInvoke для объекта, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="f7554-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7554-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7554-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7554-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7554-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="f7554-106">окне `mdFieldDef` Токен или `mdParamDef` , представляющий поле или параметр, для которого необходимо удалить подпись метаданных упаковки.</span><span class="sxs-lookup"><span data-stu-id="f7554-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7554-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f7554-107">Requirements</span></span>  

 <span data-ttu-id="f7554-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7554-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7554-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f7554-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7554-110">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7554-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7554-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7554-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7554-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f7554-112">See also</span></span>

- [<span data-ttu-id="f7554-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f7554-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f7554-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f7554-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
