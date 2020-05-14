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
ms.openlocfilehash: dd5baa282d15d121b62b4dc4dd41bcf9ff393570
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395882"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="67e89-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="67e89-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="67e89-103">Предоставляет уведомления о событиях машинного кода, которые не связаны напрямую с общеязыковой средой выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="67e89-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67e89-104">Методы</span><span class="sxs-lookup"><span data-stu-id="67e89-104">Methods</span></span>  
  
|<span data-ttu-id="67e89-105">Метод</span><span class="sxs-lookup"><span data-stu-id="67e89-105">Method</span></span>|<span data-ttu-id="67e89-106">Описание</span><span class="sxs-lookup"><span data-stu-id="67e89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67e89-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="67e89-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="67e89-108">Уведомляет отладчик о срабатывании собственного события.</span><span class="sxs-lookup"><span data-stu-id="67e89-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67e89-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="67e89-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67e89-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="67e89-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e89-111">Требования</span><span class="sxs-lookup"><span data-stu-id="67e89-111">Requirements</span></span>  
 <span data-ttu-id="67e89-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67e89-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e89-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67e89-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67e89-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67e89-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67e89-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e89-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e89-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="67e89-116">See also</span></span>

- [<span data-ttu-id="67e89-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67e89-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
