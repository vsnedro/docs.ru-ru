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
ms.openlocfilehash: 5de62db4180a6a9160193053fe42e39cebc34d0e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492500"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="cdaa2-102">Метод IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="cdaa2-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="cdaa2-103">Закрывает перечислитель, идентифицируемый указанным маркером.</span><span class="sxs-lookup"><span data-stu-id="cdaa2-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdaa2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdaa2-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdaa2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cdaa2-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="cdaa2-106">окне Маркер для закрытия перечислителя.</span><span class="sxs-lookup"><span data-stu-id="cdaa2-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdaa2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cdaa2-107">Remarks</span></span>  
 <span data-ttu-id="cdaa2-108">Маркер, заданный параметром, `hEnum` получается из предыдущего `Enum` вызова *имени* (например, [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="cdaa2-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdaa2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cdaa2-109">Requirements</span></span>  
 <span data-ttu-id="cdaa2-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdaa2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdaa2-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cdaa2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cdaa2-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cdaa2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cdaa2-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdaa2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdaa2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cdaa2-114">See also</span></span>

- [<span data-ttu-id="cdaa2-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="cdaa2-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cdaa2-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="cdaa2-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
