---
title: Метод IMetaDataImport::GetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711264"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="e1a15-102">Метод IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="e1a15-102">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="e1a15-103">Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="e1a15-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1a15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1a15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1a15-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="e1a15-106">окне Токен TypeDef для класса с макетом, который должен быть возвращен.</span><span class="sxs-lookup"><span data-stu-id="e1a15-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="e1a15-107">заполняет Одно из значений 1, 2, 4, 8 или 16, представляющее размер пакета класса.</span><span class="sxs-lookup"><span data-stu-id="e1a15-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="e1a15-108">заполняет Массив значений [COR_FIELD_OFFSET](cor-field-offset-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="e1a15-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e1a15-109">[in] Максимальный размер массива `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="e1a15-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="e1a15-110">заполняет Число элементов, возвращаемых в `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="e1a15-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="e1a15-111">заполняет Размер в байтах класса, представленного параметром `td` .</span><span class="sxs-lookup"><span data-stu-id="e1a15-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a15-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e1a15-112">Requirements</span></span>  

 <span data-ttu-id="e1a15-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1a15-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a15-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e1a15-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1a15-115">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1a15-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1a15-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a15-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a15-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1a15-117">See also</span></span>

- [<span data-ttu-id="e1a15-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e1a15-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e1a15-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e1a15-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
