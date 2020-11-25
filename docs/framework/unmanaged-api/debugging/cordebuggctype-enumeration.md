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
ms.openlocfilehash: 6b3075613af0403527ecf67d574c0f5733a5cd8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712616"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="66a75-102">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="66a75-102">CorDebugGCType Enumeration</span></span>

<span data-ttu-id="66a75-103">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="66a75-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66a75-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="66a75-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66a75-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="66a75-106">Элементы</span><span class="sxs-lookup"><span data-stu-id="66a75-106">Members</span></span>  
  
|<span data-ttu-id="66a75-107">Имя участника</span><span class="sxs-lookup"><span data-stu-id="66a75-107">Member name</span></span>|<span data-ttu-id="66a75-108">Описание</span><span class="sxs-lookup"><span data-stu-id="66a75-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="66a75-109">Сборщик мусора работает на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="66a75-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="66a75-110">Сборщик мусора работает на сервере.</span><span class="sxs-lookup"><span data-stu-id="66a75-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66a75-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="66a75-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66a75-112">Требования</span><span class="sxs-lookup"><span data-stu-id="66a75-112">Requirements</span></span>  

 <span data-ttu-id="66a75-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66a75-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a75-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66a75-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66a75-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66a75-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66a75-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a75-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a75-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66a75-117">See also</span></span>

- [<span data-ttu-id="66a75-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="66a75-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
