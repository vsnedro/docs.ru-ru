---
title: Структура ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009435"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="39d2e-102">Структура ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="39d2e-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="39d2e-103">Содержит сведения о сборке, на которую имеется ссылка, включая ее версию и уровень поддержки языковых стандартов, процессоров и операционных систем.</span><span class="sxs-lookup"><span data-stu-id="39d2e-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39d2e-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="39d2e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="39d2e-105">Members</span></span>  
  
|<span data-ttu-id="39d2e-106">Член</span><span class="sxs-lookup"><span data-stu-id="39d2e-106">Member</span></span>|<span data-ttu-id="39d2e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="39d2e-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="39d2e-108">Основной номер версии сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="39d2e-109">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="39d2e-109">This value cannot be zero.</span></span> <span data-ttu-id="39d2e-110">Если заданы все биты `usMajorVersion` , основной номер версии не указывается.</span><span class="sxs-lookup"><span data-stu-id="39d2e-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="39d2e-111">Дополнительный номер версии сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="39d2e-112">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="39d2e-112">This value cannot be zero.</span></span> <span data-ttu-id="39d2e-113">Если заданы все биты `usMinorVersion` , дополнительный номер версии не указывается.</span><span class="sxs-lookup"><span data-stu-id="39d2e-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="39d2e-114">Номер построения сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="39d2e-115">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="39d2e-115">This value cannot be zero.</span></span> <span data-ttu-id="39d2e-116">Если заданы все биты `usBuildNumber` , номер сборки не указывается.</span><span class="sxs-lookup"><span data-stu-id="39d2e-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="39d2e-117">Номер редакции сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="39d2e-118">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="39d2e-118">This value cannot be zero.</span></span> <span data-ttu-id="39d2e-119">Если заданы все биты `usRevisionNumber` , номер редакции не указывается.</span><span class="sxs-lookup"><span data-stu-id="39d2e-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="39d2e-120">Список имен языковых стандартов, которым соответствует спецификация RFC1766, разделенные точкой с запятой, с указанием языковых стандартов, поддерживаемых сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="39d2e-121">Значение NULL указывает на независимость от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="39d2e-121">A null value indicates locale independence.</span></span> <span data-ttu-id="39d2e-122">**Примечание.**  В .NET Framework версии 1,0 нельзя указать более одного языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="39d2e-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="39d2e-123">Размер в расширенных символах `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="39d2e-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="39d2e-124">Массив идентификаторов, как определено в Winnt. h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="39d2e-125">Значение NULL указывает на независимость от процессора.</span><span class="sxs-lookup"><span data-stu-id="39d2e-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="39d2e-126">Длина массива `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="39d2e-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="39d2e-127">Массив экземпляров [OSInfo](osinfo-structure.md) , указывающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="39d2e-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="39d2e-128">Значение NULL указывает на независимость от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="39d2e-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="39d2e-129">Длина массива `rOS`.</span><span class="sxs-lookup"><span data-stu-id="39d2e-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39d2e-130">Требования</span><span class="sxs-lookup"><span data-stu-id="39d2e-130">Requirements</span></span>  
 <span data-ttu-id="39d2e-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39d2e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39d2e-132">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="39d2e-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39d2e-133">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="39d2e-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39d2e-134">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39d2e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d2e-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="39d2e-135">See also</span></span>

- [<span data-ttu-id="39d2e-136">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="39d2e-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="39d2e-137">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="39d2e-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="39d2e-138">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="39d2e-138">OSINFO Structure</span></span>](osinfo-structure.md)
