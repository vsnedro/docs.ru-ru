---
title: Метод IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 26b345567699c5780827ed835cff13069ea8f609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702749"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="ba7e4-102">Метод IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="ba7e4-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>

<span data-ttu-id="ba7e4-103">Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.</span><span class="sxs-lookup"><span data-stu-id="ba7e4-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba7e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba7e4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="ba7e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba7e4-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="ba7e4-106">[вход, выход] Указатель на перечислитель для `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="ba7e4-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="ba7e4-107">окне Токен MemberRef или MethodDef, представляющий метод, для которого необходимо перечислить маркеры MethodSpec.</span><span class="sxs-lookup"><span data-stu-id="ba7e4-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="ba7e4-108">Если значение `tk` равно 0 (нулю), будут перечислены все токены MethodSpec в области.</span><span class="sxs-lookup"><span data-stu-id="ba7e4-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="ba7e4-109">заполняет Массив токенов MethodSpec для перечисления.</span><span class="sxs-lookup"><span data-stu-id="ba7e4-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ba7e4-110">окне Запрошенное максимальное число токенов для размещения в `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="ba7e4-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="ba7e4-111">заполняет Возвращенное число токенов, помещенных в `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="ba7e4-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba7e4-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba7e4-112">Return Value</span></span>  
  
|<span data-ttu-id="ba7e4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba7e4-113">HRESULT</span></span>|<span data-ttu-id="ba7e4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ba7e4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba7e4-115">`EnumMethodSpecs` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ba7e4-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ba7e4-116">`phEnum` не содержит элементов Member.</span><span class="sxs-lookup"><span data-stu-id="ba7e4-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="ba7e4-117">В этом случае `pcMethodSpecs` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="ba7e4-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba7e4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ba7e4-118">Requirements</span></span>  

 <span data-ttu-id="ba7e4-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba7e4-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba7e4-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ba7e4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba7e4-121">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba7e4-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba7e4-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba7e4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7e4-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ba7e4-123">See also</span></span>

- [<span data-ttu-id="ba7e4-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ba7e4-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="ba7e4-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ba7e4-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
