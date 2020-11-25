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
ms.openlocfilehash: 8071c3f43775975de37e3255582b6fc8f13f7de3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732792"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="43da8-102">Структура ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="43da8-102">ASSEMBLYMETADATA Structure</span></span>

<span data-ttu-id="43da8-103">Содержит сведения о сборке, на которую имеется ссылка, включая ее версию и уровень поддержки языковых стандартов, процессоров и операционных систем.</span><span class="sxs-lookup"><span data-stu-id="43da8-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43da8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43da8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="43da8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="43da8-105">Members</span></span>  
  
|<span data-ttu-id="43da8-106">Член</span><span class="sxs-lookup"><span data-stu-id="43da8-106">Member</span></span>|<span data-ttu-id="43da8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="43da8-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="43da8-108">Основной номер версии сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="43da8-109">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="43da8-109">This value cannot be zero.</span></span> <span data-ttu-id="43da8-110">Если заданы все биты `usMajorVersion` , основной номер версии не указывается.</span><span class="sxs-lookup"><span data-stu-id="43da8-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="43da8-111">Дополнительный номер версии сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="43da8-112">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="43da8-112">This value cannot be zero.</span></span> <span data-ttu-id="43da8-113">Если заданы все биты `usMinorVersion` , дополнительный номер версии не указывается.</span><span class="sxs-lookup"><span data-stu-id="43da8-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="43da8-114">Номер построения сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="43da8-115">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="43da8-115">This value cannot be zero.</span></span> <span data-ttu-id="43da8-116">Если заданы все биты `usBuildNumber` , номер сборки не указывается.</span><span class="sxs-lookup"><span data-stu-id="43da8-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="43da8-117">Номер редакции сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="43da8-118">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="43da8-118">This value cannot be zero.</span></span> <span data-ttu-id="43da8-119">Если заданы все биты `usRevisionNumber` , номер редакции не указывается.</span><span class="sxs-lookup"><span data-stu-id="43da8-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="43da8-120">Список имен языковых стандартов, которым соответствует спецификация RFC1766, разделенные точкой с запятой, с указанием языковых стандартов, поддерживаемых сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="43da8-121">Значение NULL указывает на независимость от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="43da8-121">A null value indicates locale independence.</span></span> <span data-ttu-id="43da8-122">**Примечание.**  В .NET Framework версии 1,0 нельзя указать более одного языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="43da8-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="43da8-123">Размер в расширенных символах `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="43da8-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="43da8-124">Массив идентификаторов, как определено в Winnt. h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="43da8-125">Значение NULL указывает на независимость от процессора.</span><span class="sxs-lookup"><span data-stu-id="43da8-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="43da8-126">Длина массива `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="43da8-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="43da8-127">Массив экземпляров [OSInfo](osinfo-structure.md) , указывающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="43da8-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="43da8-128">Значение NULL указывает на независимость от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="43da8-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="43da8-129">Длина массива `rOS`.</span><span class="sxs-lookup"><span data-stu-id="43da8-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43da8-130">Требования</span><span class="sxs-lookup"><span data-stu-id="43da8-130">Requirements</span></span>  

 <span data-ttu-id="43da8-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43da8-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43da8-132">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="43da8-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43da8-133">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43da8-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43da8-134">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43da8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43da8-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43da8-135">See also</span></span>

- [<span data-ttu-id="43da8-136">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="43da8-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="43da8-137">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="43da8-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="43da8-138">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="43da8-138">OSINFO Structure</span></span>](osinfo-structure.md)
