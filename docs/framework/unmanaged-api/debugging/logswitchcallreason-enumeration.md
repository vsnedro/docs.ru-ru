---
title: Перечисление LogSwitchCallReason
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
ms.openlocfilehash: dfb34595530a47b74762610f5824b68ea00a8a69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671959"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="739fc-102">Перечисление LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="739fc-102">LogSwitchCallReason Enumeration</span></span>

<span data-ttu-id="739fc-103">Указывает операцию, выполненную на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="739fc-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="739fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="739fc-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="739fc-105">Члены</span><span class="sxs-lookup"><span data-stu-id="739fc-105">Members</span></span>  
  
|<span data-ttu-id="739fc-106">Член</span><span class="sxs-lookup"><span data-stu-id="739fc-106">Member</span></span>|<span data-ttu-id="739fc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="739fc-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="739fc-108">Был создан переключатель отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="739fc-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="739fc-109">Изменен параметр отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="739fc-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="739fc-110">Удален параметр отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="739fc-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="739fc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="739fc-111">Requirements</span></span>  

 <span data-ttu-id="739fc-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="739fc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="739fc-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="739fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="739fc-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="739fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="739fc-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="739fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="739fc-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="739fc-116">See also</span></span>

- [<span data-ttu-id="739fc-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="739fc-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
