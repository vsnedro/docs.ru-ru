---
title: Перечисление CorDebugExceptionUnwindCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
ms.openlocfilehash: 30de1448a7d1452e1e9049411010e7f43d13eb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712642"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="f3ee6-102">Перечисление CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="f3ee6-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>

<span data-ttu-id="f3ee6-103">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="f3ee6-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ee6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3ee6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="f3ee6-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f3ee6-105">Members</span></span>  
  
|<span data-ttu-id="f3ee6-106">Член</span><span class="sxs-lookup"><span data-stu-id="f3ee6-106">Member</span></span>|<span data-ttu-id="f3ee6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f3ee6-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="f3ee6-108">Начало процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="f3ee6-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="f3ee6-109">Исключение перехвачено.</span><span class="sxs-lookup"><span data-stu-id="f3ee6-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3ee6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f3ee6-110">Requirements</span></span>  

 <span data-ttu-id="f3ee6-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3ee6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ee6-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3ee6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3ee6-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3ee6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3ee6-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ee6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ee6-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3ee6-115">See also</span></span>

- [<span data-ttu-id="f3ee6-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="f3ee6-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
