---
title: Перечисление CorDebugHandleType
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
ms.openlocfilehash: a0ec83a5590e184b9ff60449a8147d1a3c90a6a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712460"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="c560b-102">Перечисление CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="c560b-102">CorDebugHandleType Enumeration</span></span>

<span data-ttu-id="c560b-103">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="c560b-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c560b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c560b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="c560b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c560b-105">Members</span></span>  
  
|<span data-ttu-id="c560b-106">Член</span><span class="sxs-lookup"><span data-stu-id="c560b-106">Member</span></span>|<span data-ttu-id="c560b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c560b-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="c560b-108">Этот маркер является строгим, что предотвращает освобождение объекта при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c560b-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="c560b-109">Этот маркер является слабым, который не предотвращает освобождение объекта при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c560b-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="c560b-110">При сборе объекта этот маркер становится недействительным.</span><span class="sxs-lookup"><span data-stu-id="c560b-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c560b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c560b-111">Requirements</span></span>  

 <span data-ttu-id="c560b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c560b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c560b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c560b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c560b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c560b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c560b-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c560b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c560b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c560b-116">See also</span></span>

- [<span data-ttu-id="c560b-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c560b-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
