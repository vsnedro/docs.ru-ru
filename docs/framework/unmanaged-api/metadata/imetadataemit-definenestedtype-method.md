---
title: Метод IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719545"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="778ef-102">Метод IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="778ef-102">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="778ef-103">Создает сигнатуру метаданных определения типа, возвращает `mdTypeDef` маркер для этого типа и указывает, что определенный тип является членом типа, на который ссылается `tdEncloser` параметр.</span><span class="sxs-lookup"><span data-stu-id="778ef-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="778ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="778ef-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="778ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="778ef-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="778ef-106">окне Имя типа в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="778ef-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="778ef-107">[входные] `TypeDef` атрибута.</span><span class="sxs-lookup"><span data-stu-id="778ef-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="778ef-108">Это битовая маска `CorTypeAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="778ef-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="778ef-109">окне Маркер базового класса.</span><span class="sxs-lookup"><span data-stu-id="778ef-109">[in] The token of the base class.</span></span> <span data-ttu-id="778ef-110">Это либо маркер, либо `mdTypeDef` `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="778ef-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="778ef-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="778ef-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="778ef-112">окне Массив токенов, задающих интерфейсы, реализуемые этим классом или интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="778ef-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="778ef-113">окне Токен включающего типа.</span><span class="sxs-lookup"><span data-stu-id="778ef-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="778ef-114">Последний элемент массива должен быть `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="778ef-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="778ef-115">заполняет `mdTypeDef` Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="778ef-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="778ef-116">Требования</span><span class="sxs-lookup"><span data-stu-id="778ef-116">Requirements</span></span>  

 <span data-ttu-id="778ef-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="778ef-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="778ef-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="778ef-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="778ef-119">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="778ef-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="778ef-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="778ef-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778ef-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="778ef-121">See also</span></span>

- [<span data-ttu-id="778ef-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="778ef-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="778ef-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="778ef-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
