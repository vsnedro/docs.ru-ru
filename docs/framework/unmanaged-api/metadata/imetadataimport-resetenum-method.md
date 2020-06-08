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
ms.openlocfilehash: bc7f1740d666211b63cd93e6f1c0e6955f61ec5d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503462"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="c45e6-102">Метод IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="c45e6-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="c45e6-103">Возвращает заданный перечислитель в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="c45e6-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c45e6-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c45e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c45e6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c45e6-106">окне Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="c45e6-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="c45e6-107">окне Новое место для размещения перечислителя.</span><span class="sxs-lookup"><span data-stu-id="c45e6-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c45e6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c45e6-108">Requirements</span></span>  
 <span data-ttu-id="c45e6-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c45e6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c45e6-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c45e6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c45e6-111">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c45e6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c45e6-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c45e6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45e6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c45e6-113">See also</span></span>

- [<span data-ttu-id="c45e6-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c45e6-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c45e6-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c45e6-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
