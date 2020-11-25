---
title: Метод IMetaDataImport::ResetEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 52c35b3bd726d4c83c6745bf99940faa44ea7338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702855"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="5939a-102">Метод IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="5939a-102">IMetaDataImport::ResetEnum Method</span></span>

<span data-ttu-id="5939a-103">Возвращает заданный перечислитель в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="5939a-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5939a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5939a-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5939a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5939a-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="5939a-106">окне Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="5939a-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="5939a-107">окне Новое место для размещения перечислителя.</span><span class="sxs-lookup"><span data-stu-id="5939a-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5939a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5939a-108">Requirements</span></span>  

 <span data-ttu-id="5939a-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5939a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5939a-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5939a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5939a-111">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5939a-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5939a-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5939a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5939a-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5939a-113">See also</span></span>

- [<span data-ttu-id="5939a-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5939a-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5939a-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5939a-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
