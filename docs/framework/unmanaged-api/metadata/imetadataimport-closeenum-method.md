---
title: Метод IMetaDataImport::CloseEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
ms.openlocfilehash: f418b48f1b62ae8093197d64ca44b2ef659990a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701722"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="9279e-102">Метод IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="9279e-102">IMetaDataImport::CloseEnum Method</span></span>

<span data-ttu-id="9279e-103">Закрывает перечислитель, идентифицируемый указанным маркером.</span><span class="sxs-lookup"><span data-stu-id="9279e-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9279e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9279e-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9279e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9279e-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="9279e-106">окне Маркер для закрытия перечислителя.</span><span class="sxs-lookup"><span data-stu-id="9279e-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9279e-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9279e-107">Remarks</span></span>  

 <span data-ttu-id="9279e-108">Маркер, заданный параметром, `hEnum` получается из предыдущего `Enum` вызова *имени* (например, [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="9279e-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9279e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9279e-109">Requirements</span></span>  

 <span data-ttu-id="9279e-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9279e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9279e-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9279e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9279e-112">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9279e-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9279e-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9279e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9279e-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9279e-114">See also</span></span>

- [<span data-ttu-id="9279e-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9279e-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="9279e-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9279e-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
