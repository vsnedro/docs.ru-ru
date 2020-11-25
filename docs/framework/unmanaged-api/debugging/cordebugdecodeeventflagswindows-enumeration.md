---
title: Перечисление CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: 60eab923aac5dea927105e8ca9fa77eb5708f5ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733364"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="97c00-102">Перечисление CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="97c00-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>

<span data-ttu-id="97c00-103">Предоставляет дополнительную информацию о событиях отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="97c00-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97c00-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="97c00-105">Члены</span><span class="sxs-lookup"><span data-stu-id="97c00-105">Members</span></span>  
  
|<span data-ttu-id="97c00-106">Член</span><span class="sxs-lookup"><span data-stu-id="97c00-106">Member</span></span>|<span data-ttu-id="97c00-107">Описание</span><span class="sxs-lookup"><span data-stu-id="97c00-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="97c00-108">Указывает, что событие отладки является первичным исключением.</span><span class="sxs-lookup"><span data-stu-id="97c00-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97c00-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="97c00-109">Remarks</span></span>  

 <span data-ttu-id="97c00-110">Метод [ICorDebugProcess6::D екодивент](icordebugprocess6-decodeevent-method.md) включает `dwFlags` параметр, предоставляющий дополнительные сведения о событии отладки, значение которого зависит от целевой архитектуры.</span><span class="sxs-lookup"><span data-stu-id="97c00-110">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="97c00-111">Перечисление `CorDebugDecodeEventFlagsWindows` можно использовать с событиями отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="97c00-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97c00-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="97c00-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c00-113">Требования</span><span class="sxs-lookup"><span data-stu-id="97c00-113">Requirements</span></span>  

 <span data-ttu-id="97c00-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97c00-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97c00-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97c00-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97c00-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97c00-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97c00-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97c00-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c00-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="97c00-118">See also</span></span>

- [<span data-ttu-id="97c00-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="97c00-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
