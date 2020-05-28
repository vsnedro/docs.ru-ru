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
ms.openlocfilehash: b05527f118de059c674ea659b1a22b7895126cf4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007771"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="cd64d-102">Метод IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="cd64d-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="cd64d-103">Задает функции типа, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="cd64d-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd64d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd64d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd64d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd64d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="cd64d-106">окне `mdTypeDef`Маркер, полученный из исходного вызова [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="cd64d-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="cd64d-107">[входные] `TypeDef` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cd64d-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="cd64d-108">Это битовая маска `CorTypeAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="cd64d-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="cd64d-109">окне `mdToken`Класс базового класса.</span><span class="sxs-lookup"><span data-stu-id="cd64d-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="cd64d-110">Получено из предыдущего вызова [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md)или `null` .</span><span class="sxs-lookup"><span data-stu-id="cd64d-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="cd64d-111">окне Массив токенов для интерфейсов, реализуемых этим типом.</span><span class="sxs-lookup"><span data-stu-id="cd64d-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="cd64d-112">Эти `mdTypeRef` токены получаются с помощью [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="cd64d-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="cd64d-113">Последним элементом массива должен быть `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="cd64d-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd64d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cd64d-114">Requirements</span></span>  
 <span data-ttu-id="cd64d-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd64d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd64d-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cd64d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd64d-117">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd64d-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd64d-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd64d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd64d-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="cd64d-119">See also</span></span>

- [<span data-ttu-id="cd64d-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cd64d-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cd64d-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cd64d-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
