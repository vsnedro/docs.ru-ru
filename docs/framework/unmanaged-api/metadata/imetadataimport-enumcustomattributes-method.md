---
title: Метод IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 3b12200dae23a7b6a2f6e1654e46fdf74dc90968
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700539"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="79a9d-102">Метод IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="79a9d-102">IMetaDataImport::EnumCustomAttributes Method</span></span>

<span data-ttu-id="79a9d-103">Перечисляет токены определения пользовательских атрибутов, связанные с указанным типом или членом.</span><span class="sxs-lookup"><span data-stu-id="79a9d-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79a9d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79a9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79a9d-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="79a9d-106">[вход, выход] Указатель на возвращаемый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="79a9d-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="79a9d-107">окне Токен для области перечисления или ноль для всех настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="79a9d-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="79a9d-108">окне Токен для конструктора типа атрибутов для перечисления или `null` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="79a9d-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="79a9d-109">заполняет Массив токенов настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="79a9d-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="79a9d-110">[in] Максимальный размер массива `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="79a9d-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="79a9d-111">[out, необязательно] Фактическое число значений токена, возвращаемых в `rCustomAttributes` .</span><span class="sxs-lookup"><span data-stu-id="79a9d-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79a9d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="79a9d-112">Return Value</span></span>  
  
|<span data-ttu-id="79a9d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79a9d-113">HRESULT</span></span>|<span data-ttu-id="79a9d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="79a9d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="79a9d-115">`EnumCustomAttributes` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="79a9d-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="79a9d-116">Нет настраиваемых атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="79a9d-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="79a9d-117">В этом случае значение `pcCustomAttributes` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="79a9d-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79a9d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="79a9d-118">Requirements</span></span>  

 <span data-ttu-id="79a9d-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79a9d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a9d-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="79a9d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79a9d-121">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79a9d-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79a9d-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a9d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a9d-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79a9d-123">See also</span></span>

- [<span data-ttu-id="79a9d-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="79a9d-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="79a9d-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="79a9d-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
