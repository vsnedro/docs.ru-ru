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
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714761"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="9392e-102">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="9392e-102">IMetaDataAssemblyImport Interface</span></span>

<span data-ttu-id="9392e-103">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="9392e-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9392e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9392e-104">Methods</span></span>  
  
|<span data-ttu-id="9392e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9392e-105">Method</span></span>|<span data-ttu-id="9392e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9392e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9392e-107">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="9392e-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="9392e-108">Освобождает дескриптор указанного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="9392e-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="9392e-109">Метод EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="9392e-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="9392e-110">Возвращает указатель интерфейса на перечислитель, содержащий `mdAssemblyRef` маркеры сборок, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9392e-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9392e-111">Метод EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="9392e-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="9392e-112">Возвращает указатель интерфейса на перечислитель, содержащий `mdExportedType` маркеры COM-типов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9392e-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9392e-113">Метод EnumFiles</span><span class="sxs-lookup"><span data-stu-id="9392e-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="9392e-114">Возвращает указатель интерфейса на перечислитель, содержащий `mdFile` маркеры файлов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9392e-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9392e-115">Метод EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="9392e-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="9392e-116">Возвращает указатель интерфейса на перечислитель, содержащий `mdManifestResource` маркеры ресурсов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9392e-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9392e-117">Метод FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="9392e-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="9392e-118">Возвращает массив `mdAssemblyRef` токенов для сборок с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9392e-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="9392e-119">Метод FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="9392e-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="9392e-120">Возвращает `mdExportedType` токен для типа COM с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9392e-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="9392e-121">Метод FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="9392e-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="9392e-122">Возвращает `mdManifestResource` токен для ресурса с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9392e-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="9392e-123">Метод GetAssemblyFromScop</span><span class="sxs-lookup"><span data-stu-id="9392e-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="9392e-124">Возвращает токен для сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9392e-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9392e-125">Метод GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="9392e-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="9392e-126">Возвращает параметры свойства указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="9392e-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="9392e-127">Метод GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="9392e-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="9392e-128">Возвращает параметры свойства указанного `mdAssemblyRef` токена.</span><span class="sxs-lookup"><span data-stu-id="9392e-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="9392e-129">Метод GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="9392e-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="9392e-130">Возвращает параметры свойства указанного типа COM.</span><span class="sxs-lookup"><span data-stu-id="9392e-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="9392e-131">Метод GetFileProps</span><span class="sxs-lookup"><span data-stu-id="9392e-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="9392e-132">Возвращает настройки свойств указанного файла.</span><span class="sxs-lookup"><span data-stu-id="9392e-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="9392e-133">Метод GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="9392e-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="9392e-134">Возвращает параметры свойства указанного ресурса манифеста.</span><span class="sxs-lookup"><span data-stu-id="9392e-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9392e-135">Требования</span><span class="sxs-lookup"><span data-stu-id="9392e-135">Requirements</span></span>  

 <span data-ttu-id="9392e-136">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9392e-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9392e-137">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9392e-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9392e-138">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9392e-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9392e-139">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9392e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9392e-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9392e-140">See also</span></span>

- [<span data-ttu-id="9392e-141">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="9392e-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="9392e-142">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="9392e-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
