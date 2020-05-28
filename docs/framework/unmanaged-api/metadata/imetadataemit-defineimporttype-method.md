---
title: Метод IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: edce5cb93b770fb5730e5a06633ffffacf332f7a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004700"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="b65c0-102">Метод IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="b65c0-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="b65c0-103">Создает ссылку на указанный тип, определенный вне текущей области, и определяет маркер для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="b65c0-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b65c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b65c0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b65c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b65c0-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="b65c0-106">окне Интерфейс [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) , представляющий сборку, из которой импортируется целевой тип.</span><span class="sxs-lookup"><span data-stu-id="b65c0-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="b65c0-107">окне Массив, содержащий хэш для сборки, заданной параметром `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="b65c0-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="b65c0-108">[in] Число байтов в массиве `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="b65c0-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="b65c0-109">окне Интерфейс [IMetaDataImport](imetadataimport-interface.md) , представляющий область метаданных, из которой импортируется целевой тип.</span><span class="sxs-lookup"><span data-stu-id="b65c0-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="b65c0-110">окне `mdTypeDef`Токен, указывающий тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="b65c0-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="b65c0-111">окне Интерфейс [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) , представляющий сборку, в которую импортируется целевой тип.</span><span class="sxs-lookup"><span data-stu-id="b65c0-111">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="b65c0-112">заполняет `mdTypeRef`Токен, определенный в текущей области для ссылки на тип.</span><span class="sxs-lookup"><span data-stu-id="b65c0-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b65c0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b65c0-113">Remarks</span></span>  
 <span data-ttu-id="b65c0-114">Перед вызовом метода [IMetaDataEmit::D ефинеимпортмембер](imetadataemit-defineimportmember-method.md) можно использовать `DefineImportType` метод для создания ссылки на тип в текущей области для родительского класса члена или родительского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b65c0-114">Prior to calling the [IMetaDataEmit::DefineImportMember](imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b65c0-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b65c0-115">Requirements</span></span>  
 <span data-ttu-id="b65c0-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b65c0-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b65c0-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b65c0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b65c0-118">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b65c0-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b65c0-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65c0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65c0-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b65c0-120">See also</span></span>

- [<span data-ttu-id="b65c0-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b65c0-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b65c0-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b65c0-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
