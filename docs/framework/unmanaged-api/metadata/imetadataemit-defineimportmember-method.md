---
title: Метод IMetaDataEmit::DefineImportMember
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: ec8a24251ac4f0701b1adab19829078270229ced
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004599"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="e1ba3-102">Метод IMetaDataEmit::DefineImportMember</span><span class="sxs-lookup"><span data-stu-id="e1ba3-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="e1ba3-103">Создает ссылку на указанный элемент типа или модуля, который определен за пределами текущей области, и определяет маркер для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ba3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1ba3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1ba3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1ba3-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="e1ba3-106">окне Интерфейс [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) , представляющий сборку, из которой импортируется целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e1ba3-107">окне Массив, содержащий хэш для сборки, заданной параметром `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="e1ba3-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e1ba3-108">[in] Число байтов в массиве `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="e1ba3-109">окне Интерфейс [IMetaDataImport](imetadataimport-interface.md) , представляющий область метаданных, из которой импортируется целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="e1ba3-110">окне Токен метаданных, указывающий целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="e1ba3-111">Токен может быть `mdMethodDef` (для метода-члена), `mdProperty` (для свойства элемента) или `mdFieldDef` токена (для поля члена).</span><span class="sxs-lookup"><span data-stu-id="e1ba3-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="e1ba3-112">окне Интерфейс [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) , представляющий сборку, в которую импортируется целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="e1ba3-113">окне `mdTypeRef`Токен или `mdModuleRef` для типа или модуля соответственно, которому принадлежит целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="e1ba3-114">заполняет `mdMemberRef`Токен, определенный в текущей области для ссылки на элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1ba3-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1ba3-115">Remarks</span></span>  
 <span data-ttu-id="e1ba3-116">`DefineImportMember`Метод ищет элемент, заданный параметром `mbMember` , который определен в другой области, заданной параметром `pImport` , и извлекает его свойства.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="e1ba3-117">Эта информация используется для вызова метода [IMetaDataEmit::D ефинемемберреф](imetadataemit-definememberref-method.md) в текущей области для создания ссылки на элемент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="e1ba3-118">Как правило, перед использованием `DefineImportMember` метода необходимо создать в текущей области ссылку на тип или ссылку на модуль для родительского класса, интерфейса или модуля целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="e1ba3-119">Затем маркер метаданных для этой ссылки передается в `tkParent` аргумент.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="e1ba3-120">Не нужно создавать ссылку на родительский элемент целевого элемента, если он будет разрешен позже компилятором или компоновщиком.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="e1ba3-121">Подведение итогов.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-121">To summarize:</span></span>  
  
- <span data-ttu-id="e1ba3-122">Если целевой элемент является полем или методом, используйте метод [IMetaDataEmit::D ефинетиперефбинаме](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) или [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md) для создания ссылки на тип в текущей области для родительского класса члена или родительского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="e1ba3-123">Если целевой элемент является глобальной переменной или глобальной функцией (то есть не членом класса или интерфейса), используйте метод [IMetaDataEmit::D ефинемодулереф](imetadataemit-definemoduleref-method.md) , чтобы создать ссылку на модуль в текущей области для родительского модуля элемента.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="e1ba3-124">Значение, если родительский элемент целевого элемента будет разрешен позже компилятором или компоновщиком, а затем `mdTokenNil` передан `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="e1ba3-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="e1ba3-125">Единственный сценарий, в котором это применимо, — это то, что глобальная функция или глобальная переменная импортируется из OBJ-файла, который в конечном итоге будет связан с текущим модулем и объединенными метаданными.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1ba3-126">Требования</span><span class="sxs-lookup"><span data-stu-id="e1ba3-126">Requirements</span></span>  
 <span data-ttu-id="e1ba3-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1ba3-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ba3-128">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e1ba3-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1ba3-129">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e1ba3-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1ba3-130">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ba3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ba3-131">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e1ba3-131">See also</span></span>

- [<span data-ttu-id="e1ba3-132">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e1ba3-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e1ba3-133">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e1ba3-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
