---
title: Метод IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 81d6c972b53221ee53cbcf31639d65c30858b48b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008162"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="e038f-102">Метод IMetaDataAssemblyEmit::DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="e038f-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="e038f-103">Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="e038f-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e038f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e038f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e038f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e038f-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e038f-106">окне Имя экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="e038f-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="e038f-107">Для версии 1,1 среды CLR имя экспортируемого типа должно точно совпадать с именем, заданным в `TypeDef` для типа.</span><span class="sxs-lookup"><span data-stu-id="e038f-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="e038f-108">окне Токен, указывающий, где реализуется экспортируемый тип.</span><span class="sxs-lookup"><span data-stu-id="e038f-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="e038f-109">Допустимые значения и их связанное с ними значение:</span><span class="sxs-lookup"><span data-stu-id="e038f-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="e038f-110">`mdFile`Тип реализуется в другом файле в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="e038f-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="e038f-111">`mdAssemblyRef`Тип реализован в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="e038f-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="e038f-112">`mdExportedTYpe`Тип вложен в другой тип.</span><span class="sxs-lookup"><span data-stu-id="e038f-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="e038f-113">`mdFileNil`Тип находится в том же файле, что и манифест, и не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="e038f-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="e038f-114">окне Токен метаданных, указывающий тип для экспорта.</span><span class="sxs-lookup"><span data-stu-id="e038f-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="e038f-115">Это значение вводится в `TypeDef` таблицу в файле, который реализует тип, и имеет смысл только в том случае, если этот файл находится в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="e038f-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="e038f-116">окне Побитовое сочетание значений перечисления [кортипеаттр](cortypeattr-enumeration.md) , определяющих настройки свойств для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="e038f-116">[in] A bitwise combination of [CorTypeAttr](cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="e038f-117">заполняет Указатель на возвращаемый маркер метаданных, указывающий на экспортируемый тип.</span><span class="sxs-lookup"><span data-stu-id="e038f-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e038f-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="e038f-118">Remarks</span></span>  
 <span data-ttu-id="e038f-119">`ExportedType`Структура метаданных должна быть определена для каждого типа, предоставляемого этой сборкой и реализованного в модуле, отличном от того, который содержит манифест.</span><span class="sxs-lookup"><span data-stu-id="e038f-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e038f-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e038f-120">Requirements</span></span>  
 <span data-ttu-id="e038f-121">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e038f-121">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e038f-122">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e038f-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e038f-123">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e038f-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e038f-124">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e038f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e038f-125">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e038f-125">See also</span></span>

- [<span data-ttu-id="e038f-126">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="e038f-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
