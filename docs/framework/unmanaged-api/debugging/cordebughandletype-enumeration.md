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
ms.openlocfilehash: 2d296c1778e00c4c72e860e0705994518d1481e8
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795889"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="f0cff-102">Перечисление CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="f0cff-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="f0cff-103">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="f0cff-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0cff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0cff-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="f0cff-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f0cff-105">Members</span></span>  
  
|<span data-ttu-id="f0cff-106">Участник</span><span class="sxs-lookup"><span data-stu-id="f0cff-106">Member</span></span>|<span data-ttu-id="f0cff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f0cff-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="f0cff-108">Этот маркер является строгим, что предотвращает освобождение объекта при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f0cff-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="f0cff-109">Этот маркер является слабым, который не предотвращает освобождение объекта при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f0cff-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="f0cff-110">При сборе объекта этот маркер становится недействительным.</span><span class="sxs-lookup"><span data-stu-id="f0cff-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0cff-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f0cff-111">Requirements</span></span>  
 <span data-ttu-id="f0cff-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0cff-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0cff-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0cff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0cff-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0cff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0cff-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0cff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0cff-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f0cff-116">See also</span></span>

- [<span data-ttu-id="f0cff-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="f0cff-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
