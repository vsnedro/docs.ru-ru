---
title: Метод IMetaDataImport::EnumMethodsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 5b5345fc4819716dc6c2a00323f94546cfc67f32
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720936"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="8be6b-102">Метод IMetaDataImport::EnumMethodsWithName</span><span class="sxs-lookup"><span data-stu-id="8be6b-102">IMetaDataImport::EnumMethodsWithName Method</span></span>

<span data-ttu-id="8be6b-103">Перечисляет методы с заданным именем, определяемые по типу, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="8be6b-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8be6b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8be6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8be6b-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="8be6b-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="8be6b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8be6b-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="8be6b-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="8be6b-108">окне Токен TypeDef, представляющий тип, методы которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="8be6b-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="8be6b-109">окне Имя, ограничивающее область перечисления.</span><span class="sxs-lookup"><span data-stu-id="8be6b-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="8be6b-110">заполняет Массив, используемый для хранения маркеров MethodDef.</span><span class="sxs-lookup"><span data-stu-id="8be6b-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8be6b-111">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="8be6b-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8be6b-112">заполняет Число токенов MethodDef, возвращаемых в `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="8be6b-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8be6b-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8be6b-113">Remarks</span></span>  

 <span data-ttu-id="8be6b-114">Этот метод перечисляет поля и методы, но не свойства или события.</span><span class="sxs-lookup"><span data-stu-id="8be6b-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="8be6b-115">В отличие от метода [IMetaDataImport:: enummethods-](imetadataimport-enummethods-method.md), `EnumMethodsWithName` отменяет все маркеры методов, у которых нет указанного имени.</span><span class="sxs-lookup"><span data-stu-id="8be6b-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8be6b-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8be6b-116">Return Value</span></span>  
  
|<span data-ttu-id="8be6b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8be6b-117">HRESULT</span></span>|<span data-ttu-id="8be6b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8be6b-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8be6b-119">`EnumMethodsWithName` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="8be6b-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8be6b-120">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8be6b-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="8be6b-121">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="8be6b-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8be6b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8be6b-122">Requirements</span></span>  

 <span data-ttu-id="8be6b-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be6b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be6b-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8be6b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8be6b-125">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8be6b-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8be6b-126">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be6b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be6b-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8be6b-127">See also</span></span>

- [<span data-ttu-id="8be6b-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8be6b-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8be6b-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8be6b-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
