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
ms.openlocfilehash: e77520552eea9b58e4358cc5928e5ce666037009
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678159"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="c3296-102">Метод IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="c3296-102">IMetaDataImport::EnumTypeRefs Method</span></span>

<span data-ttu-id="c3296-103">Перечисляет токены TypeRef, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c3296-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3296-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3296-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3296-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3296-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="c3296-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="c3296-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c3296-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="c3296-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="c3296-108">заполняет Массив, используемый для хранения токенов TypeRef.</span><span class="sxs-lookup"><span data-stu-id="c3296-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c3296-109">[in] Максимальный размер массива `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="c3296-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="c3296-110">заполняет Указатель на число токенов TypeRef, возвращаемых в `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="c3296-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3296-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c3296-111">Return Value</span></span>  
  
|<span data-ttu-id="c3296-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3296-112">HRESULT</span></span>|<span data-ttu-id="c3296-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c3296-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c3296-114">`EnumTypeRefs` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c3296-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c3296-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="c3296-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c3296-116">В этом случае значение `pcTypeRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c3296-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3296-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c3296-117">Remarks</span></span>  

 <span data-ttu-id="c3296-118">Токен TypeRef представляет ссылку на тип.</span><span class="sxs-lookup"><span data-stu-id="c3296-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3296-119">Требования</span><span class="sxs-lookup"><span data-stu-id="c3296-119">Requirements</span></span>  

 <span data-ttu-id="c3296-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3296-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3296-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c3296-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3296-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3296-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3296-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3296-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3296-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c3296-124">See also</span></span>

- [<span data-ttu-id="c3296-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c3296-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c3296-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c3296-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
