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
ms.openlocfilehash: 2b24c2ca6907dfdb63ad934ec30557c246db174c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004360"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="cbbaf-102">Метод IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="cbbaf-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="cbbaf-103">Создает сигнатуру метаданных определения типа, возвращает `mdTypeDef` маркер для этого типа и указывает, что определенный тип является членом типа, на который ссылается `tdEncloser` параметр.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbbaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbbaf-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cbbaf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbbaf-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="cbbaf-106">окне Имя типа в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="cbbaf-107">[входные] `TypeDef` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="cbbaf-108">Это битовая маска `CorTypeAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="cbbaf-109">окне Маркер базового класса.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-109">[in] The token of the base class.</span></span> <span data-ttu-id="cbbaf-110">Это либо маркер, либо `mdTypeDef` `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="cbbaf-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="cbbaf-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="cbbaf-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="cbbaf-112">окне Массив токенов, задающих интерфейсы, реализуемые этим классом или интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="cbbaf-113">окне Токен включающего типа.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="cbbaf-114">Последний элемент массива должен быть `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="cbbaf-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="cbbaf-115">заполняет `mdTypeDef`Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="cbbaf-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbbaf-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cbbaf-116">Requirements</span></span>  
 <span data-ttu-id="cbbaf-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbbaf-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbbaf-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cbbaf-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbbaf-119">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cbbaf-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbbaf-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbbaf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbaf-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="cbbaf-121">See also</span></span>

- [<span data-ttu-id="cbbaf-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cbbaf-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cbbaf-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cbbaf-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
