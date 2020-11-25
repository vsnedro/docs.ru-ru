---
title: Перечисление CLR_DEBUGGING_PROCESS_FLAGS
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
ms.openlocfilehash: dd148d23d6e29f03052d3bbf1fcd5d02fb332a0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729854"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="a4e0a-102">Перечисление CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="a4e0a-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>

<span data-ttu-id="a4e0a-103">Предоставляет значения, используемые методом [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a4e0a-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4e0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4e0a-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a4e0a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="a4e0a-105">Members</span></span>  
  
|<span data-ttu-id="a4e0a-106">Член</span><span class="sxs-lookup"><span data-stu-id="a4e0a-106">Member</span></span>|<span data-ttu-id="a4e0a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e0a-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="a4e0a-108">Эта среда выполнения имеет управляемое событие отладчика, не являющегося перехватываться, для отправки.</span><span class="sxs-lookup"><span data-stu-id="a4e0a-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="a4e0a-109">Различия между событиями "перехват" и "не перехватывать" см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="a4e0a-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="a4e0a-110">Управляемое событие, которое является ожидающим, является <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> запросом.</span><span class="sxs-lookup"><span data-stu-id="a4e0a-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4e0a-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a4e0a-111">Remarks</span></span>  

 <span data-ttu-id="a4e0a-112">К событиям перехвата относятся процесс, домен приложения, сборка, модуль и уведомления о создании потоков, которые переводят отладчик в текущее состояние после его присоединения к процессу.</span><span class="sxs-lookup"><span data-stu-id="a4e0a-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="a4e0a-113">События, не относящиеся к перехвату, которые обозначаются `CLR_DEBUGGING_MANAGED_EVENT_PENDING` флагом, включают все остальные события отладчика, такие как исключения и уведомления помощника по отладке управляемого кода (MDA).</span><span class="sxs-lookup"><span data-stu-id="a4e0a-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="a4e0a-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`Флаг позволяет среде выполнения отличать незавершенное исключение и запрос на присоединение управляемого отладчика, который может быть отменен.</span><span class="sxs-lookup"><span data-stu-id="a4e0a-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4e0a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a4e0a-115">Requirements</span></span>  

 <span data-ttu-id="a4e0a-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4e0a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4e0a-117">**Заголовок:** Метахост. idl, Метахост. h</span><span class="sxs-lookup"><span data-stu-id="a4e0a-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="a4e0a-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4e0a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4e0a-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4e0a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4e0a-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4e0a-120">See also</span></span>

- [<span data-ttu-id="a4e0a-121">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="a4e0a-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="a4e0a-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="a4e0a-122">Debugging</span></span>](index.md)
