---
title: Метод IMetaDataImport::EnumTypeSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 38c9f8df12b0fc83a236d2cb7c32d1198be7096d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719818"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="12909-102">Метод IMetaDataImport::EnumTypeSpecs</span><span class="sxs-lookup"><span data-stu-id="12909-102">IMetaDataImport::EnumTypeSpecs Method</span></span>

<span data-ttu-id="12909-103">Перечисляет токены TypeSpec, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="12909-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12909-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12909-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12909-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12909-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="12909-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="12909-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="12909-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="12909-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="12909-108">заполняет Массив, используемый для хранения токенов TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="12909-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="12909-109">[in] Максимальный размер массива `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="12909-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="12909-110">заполняет Число токенов TypeSpec, возвращаемых в `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="12909-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12909-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="12909-111">Return Value</span></span>  
  
|<span data-ttu-id="12909-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12909-112">HRESULT</span></span>|<span data-ttu-id="12909-113">Описание</span><span class="sxs-lookup"><span data-stu-id="12909-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="12909-114">`EnumTypeSpecs` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="12909-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="12909-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="12909-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="12909-116">В этом случае значение `pcTypeSpecs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="12909-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12909-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="12909-117">Remarks</span></span>  

 <span data-ttu-id="12909-118">Токены TypeSpec создаются методом [IMetaDataEmit:: жеттокенфромтипеспек](imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="12909-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12909-119">Требования</span><span class="sxs-lookup"><span data-stu-id="12909-119">Requirements</span></span>  

 <span data-ttu-id="12909-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12909-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12909-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="12909-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12909-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12909-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12909-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12909-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12909-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12909-124">See also</span></span>

- [<span data-ttu-id="12909-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="12909-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="12909-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="12909-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
