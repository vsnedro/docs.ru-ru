---
title: Перечисление CorRegFlags
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: 5ea588194720394ad9f361fbba702f3fcdcbe110
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706103"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="e90bb-102">Перечисление CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="e90bb-102">CorRegFlags Enumeration</span></span>

<span data-ttu-id="e90bb-103">Предоставляет значения флагов, используемые для регистрации при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="e90bb-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e90bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e90bb-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e90bb-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e90bb-105">Members</span></span>  
  
|<span data-ttu-id="e90bb-106">Член</span><span class="sxs-lookup"><span data-stu-id="e90bb-106">Member</span></span>|<span data-ttu-id="e90bb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e90bb-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="e90bb-108">Указывает, что файлы не должны копироваться в место назначения.</span><span class="sxs-lookup"><span data-stu-id="e90bb-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="e90bb-109">Указывает, что модуль или составной является конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="e90bb-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="e90bb-110">Указывает, что модуль или составная ссылка содержит ссылки на классы.</span><span class="sxs-lookup"><span data-stu-id="e90bb-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e90bb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e90bb-111">Requirements</span></span>  

 <span data-ttu-id="e90bb-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e90bb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e90bb-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e90bb-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e90bb-114">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e90bb-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e90bb-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e90bb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90bb-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e90bb-116">See also</span></span>

- [<span data-ttu-id="e90bb-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="e90bb-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
