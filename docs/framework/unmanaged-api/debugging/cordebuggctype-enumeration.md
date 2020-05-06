---
title: Перечисление CorDebugGCType
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 8dd070d2c895a94ac996be81e672bd67f59b83b7
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795902"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="e33f9-102">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="e33f9-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="e33f9-103">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="e33f9-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e33f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e33f9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e33f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e33f9-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="e33f9-106">Участники</span><span class="sxs-lookup"><span data-stu-id="e33f9-106">Members</span></span>  
  
|<span data-ttu-id="e33f9-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="e33f9-107">Member name</span></span>|<span data-ttu-id="e33f9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e33f9-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="e33f9-109">Сборщик мусора работает на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="e33f9-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="e33f9-110">Сборщик мусора работает на сервере.</span><span class="sxs-lookup"><span data-stu-id="e33f9-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e33f9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e33f9-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e33f9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e33f9-112">Requirements</span></span>  
 <span data-ttu-id="e33f9-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e33f9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e33f9-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e33f9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e33f9-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e33f9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e33f9-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e33f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33f9-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e33f9-117">See also</span></span>

- [<span data-ttu-id="e33f9-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="e33f9-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
