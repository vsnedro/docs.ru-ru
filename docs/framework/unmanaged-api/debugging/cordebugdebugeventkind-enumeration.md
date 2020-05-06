---
title: Перечисление CorDebugDebugEventKind
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
ms.openlocfilehash: b7db7c9e17d87b91e09d5d010d40431cba5385df
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795993"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="2e748-102">Перечисление CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="2e748-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="2e748-103">Указывает тип события, сведения о котором декодированы методом [DecodeEvent](icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2e748-103">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e748-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e748-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="2e748-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2e748-105">Members</span></span>  
  
|<span data-ttu-id="2e748-106">Участник</span><span class="sxs-lookup"><span data-stu-id="2e748-106">Member</span></span>|<span data-ttu-id="2e748-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2e748-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="2e748-108">Событие загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="2e748-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="2e748-109">Событие выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="2e748-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="2e748-110">Первичное исключение.</span><span class="sxs-lookup"><span data-stu-id="2e748-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="2e748-111">Первичное исключение пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e748-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="2e748-112">Исключение, для которого существует обработчик `catch`.</span><span class="sxs-lookup"><span data-stu-id="2e748-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="2e748-113">Необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="2e748-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e748-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e748-114">Remarks</span></span>  
 <span data-ttu-id="2e748-115">Член `CorDebugDebugEventKind` перечисления возвращается путем вызова метода [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2e748-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e748-116">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2e748-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e748-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2e748-117">Requirements</span></span>  
 <span data-ttu-id="2e748-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e748-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e748-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e748-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e748-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e748-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e748-121">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e748-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e748-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2e748-122">See also</span></span>

- [<span data-ttu-id="2e748-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="2e748-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
