---
title: Структура OSINFO
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: ab9d7eb6f5760b43fe805443bbe1ea4a95c72069
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501070"
---
# <a name="osinfo-structure"></a><span data-ttu-id="eb40b-102">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="eb40b-102">OSINFO Structure</span></span>
<span data-ttu-id="eb40b-103">Содержит сведения об операционной системе для сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="eb40b-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb40b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb40b-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="eb40b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="eb40b-105">Members</span></span>  
  
|<span data-ttu-id="eb40b-106">Член</span><span class="sxs-lookup"><span data-stu-id="eb40b-106">Member</span></span>|<span data-ttu-id="eb40b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="eb40b-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="eb40b-108">Одно из значений идентификатора, определяемое функцией платформы Microsoft Windows `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="eb40b-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="eb40b-109">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="eb40b-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="eb40b-110">-VER_PLATFORM_WIN32s или символ 0x0000, чтобы указать Microsoft Windows 3,1.</span><span class="sxs-lookup"><span data-stu-id="eb40b-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="eb40b-111">-VER_PLATFORM_WIN32_WINDOWS или 0x0001, чтобы указать для Windows 95, Windows 98 или операционных систем по убыванию.</span><span class="sxs-lookup"><span data-stu-id="eb40b-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="eb40b-112">-VER_PLATFORM_WIN32_NT или 0x0002, чтобы указать Windows NT или операционные системы в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="eb40b-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="eb40b-113">Основной номер версии операционной системы или значение NULL для указания любой версии.</span><span class="sxs-lookup"><span data-stu-id="eb40b-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="eb40b-114">Дополнительный номер версии операционной системы или значение NULL для указания любой версии.</span><span class="sxs-lookup"><span data-stu-id="eb40b-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb40b-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb40b-115">Remarks</span></span>  
 <span data-ttu-id="eb40b-116">`OSINFO`основывается на `OSVERSIONINFOEX` структуре, используемой в вызовах функции платформы Microsoft Windows `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="eb40b-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="eb40b-117">Эта структура используется структурой ASSEMBLYMETADATA для указания поддержки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="eb40b-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb40b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="eb40b-118">Requirements</span></span>  
 <span data-ttu-id="eb40b-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb40b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb40b-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="eb40b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb40b-121">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eb40b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb40b-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb40b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb40b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="eb40b-123">See also</span></span>

- [<span data-ttu-id="eb40b-124">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="eb40b-124">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="eb40b-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="eb40b-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
