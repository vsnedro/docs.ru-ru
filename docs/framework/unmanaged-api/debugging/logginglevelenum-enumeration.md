---
title: Перечисление LoggingLevelEnum
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 62ea982f30a6a73648d9bf36722c0b5a49a68896
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420751"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="c9616-102">Перечисление LoggingLevelEnum</span><span class="sxs-lookup"><span data-stu-id="c9616-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="c9616-103">Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.</span><span class="sxs-lookup"><span data-stu-id="c9616-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9616-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9616-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="c9616-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c9616-105">Members</span></span>  
  
|<span data-ttu-id="c9616-106">Член</span><span class="sxs-lookup"><span data-stu-id="c9616-106">Member</span></span>|<span data-ttu-id="c9616-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c9616-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="c9616-108">Сообщение является уровнем трассировки 0.</span><span class="sxs-lookup"><span data-stu-id="c9616-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="c9616-109">Сообщение является уровнем трассировки 1.</span><span class="sxs-lookup"><span data-stu-id="c9616-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="c9616-110">Сообщение является уровнем трассировки 2.</span><span class="sxs-lookup"><span data-stu-id="c9616-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="c9616-111">Сообщение имеет уровень трассировки 3.</span><span class="sxs-lookup"><span data-stu-id="c9616-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="c9616-112">Сообщение имеет уровень трассировки 4.</span><span class="sxs-lookup"><span data-stu-id="c9616-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="c9616-113">Сообщение имеет уровень состояния 0.</span><span class="sxs-lookup"><span data-stu-id="c9616-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="c9616-114">Сообщение имеет уровень состояния 1.</span><span class="sxs-lookup"><span data-stu-id="c9616-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="c9616-115">Сообщение имеет уровень состояния 2.</span><span class="sxs-lookup"><span data-stu-id="c9616-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="c9616-116">Сообщение имеет уровень состояния 3.</span><span class="sxs-lookup"><span data-stu-id="c9616-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="c9616-117">Сообщение имеет уровень состояния 4.</span><span class="sxs-lookup"><span data-stu-id="c9616-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="c9616-118">Сообщение является уровнем предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c9616-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="c9616-119">Сообщение имеет уровень ошибки.</span><span class="sxs-lookup"><span data-stu-id="c9616-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="c9616-120">Сообщение имеет уровень тревоги.</span><span class="sxs-lookup"><span data-stu-id="c9616-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9616-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c9616-121">Remarks</span></span>  
 <span data-ttu-id="c9616-122">Среда CLR вызывает метод [ICorDebugManagedCallback:: LogMessage](icordebugmanagedcallback-logmessage-method.md) , чтобы уведомить отладчик о том, что управляемый поток зарегистрировал событие.</span><span class="sxs-lookup"><span data-stu-id="c9616-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="c9616-123">Среда CLR передает значение `LoggingLevelEnum` перечисления, чтобы указать степень серьезности сообщения, которое управляемый поток записал в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="c9616-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9616-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c9616-124">Requirements</span></span>  
 <span data-ttu-id="c9616-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9616-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9616-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9616-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9616-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9616-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9616-128">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9616-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9616-129">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c9616-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="c9616-130">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c9616-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
