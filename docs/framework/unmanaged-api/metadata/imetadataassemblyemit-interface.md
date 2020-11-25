---
title: Интерфейс IMetaDataAssemblyEmit
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728294"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="a27a2-102">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a27a2-102">IMetaDataAssemblyEmit Interface</span></span>

<span data-ttu-id="a27a2-103">Предоставляет методы, поддерживающие модель самоописания, которая используется средой CLR для разрешения и потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a27a2-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a27a2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a27a2-104">Methods</span></span>  
  
|<span data-ttu-id="a27a2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a27a2-105">Method</span></span>|<span data-ttu-id="a27a2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a27a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a27a2-107">Метод DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="a27a2-107">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="a27a2-108">Создает структуру данных сборки, содержащую метаданные для заданной сборки, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="a27a2-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a27a2-109">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="a27a2-109">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="a27a2-110">Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="a27a2-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a27a2-111">Метод DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="a27a2-111">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="a27a2-112">Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="a27a2-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a27a2-113">Метод DefineFile</span><span class="sxs-lookup"><span data-stu-id="a27a2-113">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="a27a2-114">Создает структуру метаданных `File`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="a27a2-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a27a2-115">Метод DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="a27a2-115">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="a27a2-116">Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="a27a2-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a27a2-117">Метод SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="a27a2-117">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="a27a2-118">Изменяет указанную структуру метаданных `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="a27a2-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="a27a2-119">Метод SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="a27a2-119">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="a27a2-120">Изменяет указанную структуру метаданных `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="a27a2-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="a27a2-121">Метод SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="a27a2-121">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="a27a2-122">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="a27a2-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="a27a2-123">Метод SetFileProps</span><span class="sxs-lookup"><span data-stu-id="a27a2-123">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="a27a2-124">Изменяет указанную структуру метаданных `File`.</span><span class="sxs-lookup"><span data-stu-id="a27a2-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="a27a2-125">Метод SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="a27a2-125">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="a27a2-126">Изменяет указанную структуру метаданных `ManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="a27a2-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a27a2-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="a27a2-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a27a2-128">Требования</span><span class="sxs-lookup"><span data-stu-id="a27a2-128">Requirements</span></span>  

 <span data-ttu-id="a27a2-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a27a2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a27a2-130">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a27a2-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a27a2-131">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a27a2-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a27a2-132">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a27a2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27a2-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a27a2-133">See also</span></span>

- [<span data-ttu-id="a27a2-134">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="a27a2-134">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="a27a2-135">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="a27a2-135">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
