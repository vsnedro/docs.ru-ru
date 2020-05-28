---
title: Интерфейс IMetaDataAssemblyImport
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 2a67f50fa1042e8d3957a9a0394507f260a328c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009019"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="a1414-102">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="a1414-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="a1414-103">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="a1414-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1414-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a1414-104">Methods</span></span>  
  
|<span data-ttu-id="a1414-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a1414-105">Method</span></span>|<span data-ttu-id="a1414-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a1414-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1414-107">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="a1414-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="a1414-108">Освобождает дескриптор указанного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a1414-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="a1414-109">Метод EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="a1414-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="a1414-110">Возвращает указатель интерфейса на перечислитель, содержащий `mdAssemblyRef` маркеры сборок, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a1414-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="a1414-111">Метод EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="a1414-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="a1414-112">Возвращает указатель интерфейса на перечислитель, содержащий `mdExportedType` маркеры COM-типов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a1414-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="a1414-113">Метод EnumFiles</span><span class="sxs-lookup"><span data-stu-id="a1414-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="a1414-114">Возвращает указатель интерфейса на перечислитель, содержащий `mdFile` маркеры файлов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a1414-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="a1414-115">Метод EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="a1414-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="a1414-116">Возвращает указатель интерфейса на перечислитель, содержащий `mdManifestResource` маркеры ресурсов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a1414-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="a1414-117">Метод FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="a1414-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="a1414-118">Возвращает массив `mdAssemblyRef` токенов для сборок с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="a1414-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="a1414-119">Метод FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="a1414-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="a1414-120">Возвращает `mdExportedType` токен для типа COM с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="a1414-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="a1414-121">Метод FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="a1414-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="a1414-122">Возвращает `mdManifestResource` токен для ресурса с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="a1414-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="a1414-123">Метод GetAssemblyFromScop</span><span class="sxs-lookup"><span data-stu-id="a1414-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="a1414-124">Возвращает токен для сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a1414-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="a1414-125">Метод GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="a1414-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="a1414-126">Возвращает параметры свойства указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="a1414-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="a1414-127">Метод GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="a1414-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="a1414-128">Возвращает параметры свойства указанного `mdAssemblyRef` токена.</span><span class="sxs-lookup"><span data-stu-id="a1414-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="a1414-129">Метод GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="a1414-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="a1414-130">Возвращает параметры свойства указанного типа COM.</span><span class="sxs-lookup"><span data-stu-id="a1414-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="a1414-131">Метод GetFileProps</span><span class="sxs-lookup"><span data-stu-id="a1414-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="a1414-132">Возвращает настройки свойств указанного файла.</span><span class="sxs-lookup"><span data-stu-id="a1414-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="a1414-133">Метод GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="a1414-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="a1414-134">Возвращает параметры свойства указанного ресурса манифеста.</span><span class="sxs-lookup"><span data-stu-id="a1414-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1414-135">Требования</span><span class="sxs-lookup"><span data-stu-id="a1414-135">Requirements</span></span>  
 <span data-ttu-id="a1414-136">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1414-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1414-137">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a1414-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1414-138">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a1414-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1414-139">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1414-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1414-140">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a1414-140">See also</span></span>

- [<span data-ttu-id="a1414-141">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="a1414-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="a1414-142">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a1414-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
