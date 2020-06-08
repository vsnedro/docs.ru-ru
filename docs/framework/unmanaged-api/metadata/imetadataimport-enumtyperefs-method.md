---
title: Метод IMetaDataImport::EnumTypeRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: 0c7e96c50e59902cde4686f908047a86dd2b6a47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503748"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="b0cce-102">Метод IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="b0cce-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="b0cce-103">Перечисляет токены TypeRef, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="b0cce-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0cce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0cce-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0cce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0cce-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b0cce-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="b0cce-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b0cce-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="b0cce-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="b0cce-108">заполняет Массив, используемый для хранения токенов TypeRef.</span><span class="sxs-lookup"><span data-stu-id="b0cce-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b0cce-109">[in] Максимальный размер массива `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="b0cce-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="b0cce-110">заполняет Указатель на число токенов TypeRef, возвращаемых в `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="b0cce-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0cce-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b0cce-111">Return Value</span></span>  
  
|<span data-ttu-id="b0cce-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0cce-112">HRESULT</span></span>|<span data-ttu-id="b0cce-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b0cce-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b0cce-114">`EnumTypeRefs`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b0cce-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b0cce-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b0cce-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b0cce-116">В этом случае значение `pcTypeRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="b0cce-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0cce-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0cce-117">Remarks</span></span>  
 <span data-ttu-id="b0cce-118">Токен TypeRef представляет ссылку на тип.</span><span class="sxs-lookup"><span data-stu-id="b0cce-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0cce-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b0cce-119">Requirements</span></span>  
 <span data-ttu-id="b0cce-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0cce-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0cce-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b0cce-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0cce-122">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b0cce-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0cce-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0cce-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0cce-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b0cce-124">See also</span></span>

- [<span data-ttu-id="b0cce-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b0cce-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b0cce-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b0cce-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
