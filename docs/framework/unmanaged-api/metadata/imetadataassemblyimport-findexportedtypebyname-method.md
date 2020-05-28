---
title: Метод IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009396"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="0c5fa-102">Метод IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="0c5fa-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="0c5fa-103">Возвращает указатель на экспортированный тип по заданному имени и включающему его типу.</span><span class="sxs-lookup"><span data-stu-id="0c5fa-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c5fa-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c5fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c5fa-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0c5fa-106">окне Имя экспортированного типа.</span><span class="sxs-lookup"><span data-stu-id="0c5fa-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="0c5fa-107">окне Токен метаданных для включающего класса экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="0c5fa-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="0c5fa-108">Это значение равно, `mdExportedTypeNil` Если запрошенный экспортированный тип не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="0c5fa-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="0c5fa-109">заполняет Указатель на `mdExportedType` маркер, представляющий экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="0c5fa-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c5fa-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c5fa-110">Remarks</span></span>  
 <span data-ttu-id="0c5fa-111">`FindExportedTypeByName`Метод использует стандартные правила, используемые средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="0c5fa-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c5fa-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0c5fa-112">Requirements</span></span>  
 <span data-ttu-id="0c5fa-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c5fa-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5fa-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="0c5fa-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c5fa-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c5fa-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c5fa-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5fa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5fa-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="0c5fa-117">See also</span></span>

- [<span data-ttu-id="0c5fa-118">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="0c5fa-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0c5fa-119">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="0c5fa-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
