---
title: Метод IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 2f572f66f16ff701350fde3b05be822b9e8c78b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706837"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="e0b46-102">Метод IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="e0b46-102">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="e0b46-103">Задает функции типа, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0b46-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0b46-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0b46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0b46-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="e0b46-106">окне `mdTypeDef` Маркер, полученный из исходного вызова [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0b46-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="e0b46-107">[входные] `TypeDef` атрибута.</span><span class="sxs-lookup"><span data-stu-id="e0b46-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="e0b46-108">Это битовая маска `CorTypeAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="e0b46-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="e0b46-109">окне `mdToken` Класс базового класса.</span><span class="sxs-lookup"><span data-stu-id="e0b46-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="e0b46-110">Получено из предыдущего вызова [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md)или `null` .</span><span class="sxs-lookup"><span data-stu-id="e0b46-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="e0b46-111">окне Массив токенов для интерфейсов, реализуемых этим типом.</span><span class="sxs-lookup"><span data-stu-id="e0b46-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="e0b46-112">Эти `mdTypeRef` токены получаются с помощью [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0b46-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="e0b46-113">Последним элементом массива должен быть `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="e0b46-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b46-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e0b46-114">Requirements</span></span>  

 <span data-ttu-id="e0b46-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b46-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b46-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e0b46-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0b46-117">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0b46-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0b46-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b46-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b46-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0b46-119">See also</span></span>

- [<span data-ttu-id="e0b46-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e0b46-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e0b46-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e0b46-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
