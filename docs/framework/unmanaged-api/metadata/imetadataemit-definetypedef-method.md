---
title: Метод IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: dc064b00e32bb6b1d8c2d0c20f571b35919eae23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009344"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="fe80c-102">Метод IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="fe80c-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="fe80c-103">Создает определение типа для типа среды CLR и получает маркер метаданных для этого определения типа.</span><span class="sxs-lookup"><span data-stu-id="fe80c-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe80c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe80c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe80c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe80c-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="fe80c-106">окне Имя типа в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="fe80c-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="fe80c-107">[входные] `TypeDef` атрибута.</span><span class="sxs-lookup"><span data-stu-id="fe80c-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="fe80c-108">Это битовая маска `CoreTypeAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="fe80c-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="fe80c-109">окне Маркер базового класса.</span><span class="sxs-lookup"><span data-stu-id="fe80c-109">[in] The token of the base class.</span></span> <span data-ttu-id="fe80c-110">Он должен быть либо `mdTypeDef` `mdTypeRef` маркером, либо.</span><span class="sxs-lookup"><span data-stu-id="fe80c-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="fe80c-111">окне Массив токенов, указывающий интерфейсы, реализуемые этим классом или интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="fe80c-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="fe80c-112">заполняет `mdTypeDef`Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="fe80c-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe80c-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe80c-113">Remarks</span></span>  
 <span data-ttu-id="fe80c-114">Флаг в `dwTypeDefFlags` указывает, является ли создаваемый тип ссылочным типом системы общих типов (класс или интерфейс) или типом значения системы общего типа.</span><span class="sxs-lookup"><span data-stu-id="fe80c-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="fe80c-115">В зависимости от предоставленных параметров этот метод, как побочный результат, может также создавать `mdInterfaceImpl` запись для каждого интерфейса, который наследуется или реализуется этим типом.</span><span class="sxs-lookup"><span data-stu-id="fe80c-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="fe80c-116">Однако этот метод не возвращает ни одного из этих `mdInterfaceImpl` токенов.</span><span class="sxs-lookup"><span data-stu-id="fe80c-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="fe80c-117">Если клиент хочет позже добавить или изменить `mdInterfaceImpl` маркер, он должен использовать `IMetaDataImport` интерфейс для перечисления.</span><span class="sxs-lookup"><span data-stu-id="fe80c-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="fe80c-118">Если вы хотите использовать семантику интерфейса COM, необходимо `[default]` предоставить интерфейс по умолчанию в качестве первого элемента в `rtkImplements` ; настраиваемый атрибут, заданный для класса, указывает, что класс имеет интерфейс по умолчанию (который всегда считается первым `mdInterfaceImpl` маркером, объявленным для класса).</span><span class="sxs-lookup"><span data-stu-id="fe80c-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="fe80c-119">Каждый элемент `rtkImplements` массива содержит `mdTypeDef` `mdTypeRef` токен или.</span><span class="sxs-lookup"><span data-stu-id="fe80c-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="fe80c-120">Последний элемент в массиве должен быть `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="fe80c-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe80c-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fe80c-121">Requirements</span></span>  
 <span data-ttu-id="fe80c-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe80c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe80c-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="fe80c-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe80c-124">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe80c-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe80c-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe80c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe80c-126">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fe80c-126">See also</span></span>

- [<span data-ttu-id="fe80c-127">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fe80c-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fe80c-128">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fe80c-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
