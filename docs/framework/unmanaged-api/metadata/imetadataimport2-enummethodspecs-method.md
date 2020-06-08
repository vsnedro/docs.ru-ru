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
ms.openlocfilehash: 8f6fbc570e7ea85aca5b365611d58a1700fb27cd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490728"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="cf6ee-102">Метод IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="cf6ee-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="cf6ee-103">Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.</span><span class="sxs-lookup"><span data-stu-id="cf6ee-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf6ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf6ee-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="cf6ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf6ee-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cf6ee-106">[вход, выход] Указатель на перечислитель для `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="cf6ee-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="cf6ee-107">окне Токен MemberRef или MethodDef, представляющий метод, для которого необходимо перечислить маркеры MethodSpec.</span><span class="sxs-lookup"><span data-stu-id="cf6ee-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="cf6ee-108">Если значение `tk` равно 0 (нулю), будут перечислены все токены MethodSpec в области.</span><span class="sxs-lookup"><span data-stu-id="cf6ee-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="cf6ee-109">заполняет Массив токенов MethodSpec для перечисления.</span><span class="sxs-lookup"><span data-stu-id="cf6ee-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cf6ee-110">окне Запрошенное максимальное число токенов для размещения в `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="cf6ee-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="cf6ee-111">заполняет Возвращенное число токенов, помещенных в `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="cf6ee-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf6ee-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cf6ee-112">Return Value</span></span>  
  
|<span data-ttu-id="cf6ee-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf6ee-113">HRESULT</span></span>|<span data-ttu-id="cf6ee-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cf6ee-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf6ee-115">`EnumMethodSpecs`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="cf6ee-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cf6ee-116">`phEnum`не содержит элементов Member.</span><span class="sxs-lookup"><span data-stu-id="cf6ee-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="cf6ee-117">В этом случае `pcMethodSpecs` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="cf6ee-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf6ee-118">Требования</span><span class="sxs-lookup"><span data-stu-id="cf6ee-118">Requirements</span></span>  
 <span data-ttu-id="cf6ee-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf6ee-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf6ee-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cf6ee-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf6ee-121">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf6ee-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf6ee-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf6ee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6ee-123">См. также</span><span class="sxs-lookup"><span data-stu-id="cf6ee-123">See also</span></span>

- [<span data-ttu-id="cf6ee-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="cf6ee-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="cf6ee-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="cf6ee-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
