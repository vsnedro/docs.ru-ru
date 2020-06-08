---
title: Метод IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 8feba8e67f3a90dd48fd957065a9c166c204b87c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492744"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="5099b-102">Метод IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="5099b-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="5099b-103">Задает значения свойств для определения универсального параметра, на которое ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="5099b-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5099b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5099b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5099b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5099b-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="5099b-106">окне Токен для определения универсального параметра, для которого задаются значения.</span><span class="sxs-lookup"><span data-stu-id="5099b-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="5099b-107">окне Значение перечисления [корженерикпараматтр](corgenericparamattr-enumeration.md) , описывающее тип универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="5099b-107">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="5099b-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="5099b-108">[in] Optional.</span></span> <span data-ttu-id="5099b-109">Имя параметра, для которого задаются значения.</span><span class="sxs-lookup"><span data-stu-id="5099b-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="5099b-110">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="5099b-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="5099b-111">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="5099b-111">[in] Optional.</span></span> <span data-ttu-id="5099b-112">Массив ограничений типа, заканчивающийся нулем.</span><span class="sxs-lookup"><span data-stu-id="5099b-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="5099b-113">Элементы массива должны быть `mdTypeDef` `mdTypeRef` `mdTypeSpec` маркером метаданных, или.</span><span class="sxs-lookup"><span data-stu-id="5099b-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5099b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5099b-114">Requirements</span></span>  
 <span data-ttu-id="5099b-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5099b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5099b-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5099b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5099b-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5099b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5099b-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5099b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5099b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5099b-119">See also</span></span>

- [<span data-ttu-id="5099b-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5099b-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="5099b-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5099b-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
