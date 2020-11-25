---
title: Интерфейс ICorDebugUnmanagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: 73722c9fbc1571496159c32b0106f25bc05dbe65
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703022"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="3612a-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="3612a-102">ICorDebugUnmanagedCallback Interface</span></span>

<span data-ttu-id="3612a-103">Предоставляет уведомления о событиях машинного кода, которые не связаны напрямую с общеязыковой средой выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="3612a-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3612a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3612a-104">Methods</span></span>  
  
|<span data-ttu-id="3612a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3612a-105">Method</span></span>|<span data-ttu-id="3612a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3612a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3612a-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="3612a-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="3612a-108">Уведомляет отладчик о срабатывании собственного события.</span><span class="sxs-lookup"><span data-stu-id="3612a-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3612a-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3612a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3612a-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3612a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3612a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3612a-111">Requirements</span></span>  

 <span data-ttu-id="3612a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3612a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3612a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3612a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3612a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3612a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3612a-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3612a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3612a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3612a-116">See also</span></span>

- [<span data-ttu-id="3612a-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3612a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
