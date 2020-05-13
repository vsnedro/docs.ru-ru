---
title: Интерфейс ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: a7a8d96548704f223f05826af79a4e227bdfab06
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379833"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="15b05-102">Интерфейс ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="15b05-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="15b05-103">Служит логическим расширением интерфейса ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="15b05-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15b05-104">Методы</span><span class="sxs-lookup"><span data-stu-id="15b05-104">Methods</span></span>  
  
|<span data-ttu-id="15b05-105">Метод</span><span class="sxs-lookup"><span data-stu-id="15b05-105">Method</span></span>|<span data-ttu-id="15b05-106">Описание</span><span class="sxs-lookup"><span data-stu-id="15b05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15b05-107">Метод GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="15b05-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="15b05-108">Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="15b05-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="15b05-109">Метод GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="15b05-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="15b05-110">Возвращает идентификатор соединения для этого `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="15b05-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="15b05-111">Метод GetTaskID</span><span class="sxs-lookup"><span data-stu-id="15b05-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="15b05-112">Возвращает идентификатор задачи для этого `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="15b05-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="15b05-113">Метод GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="15b05-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="15b05-114">Возвращает идентификатор потока операционной системы для этого `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="15b05-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="15b05-115">Метод InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="15b05-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="15b05-116">Позволяет отладчику перехватывать текущее исключение в потоке.</span><span class="sxs-lookup"><span data-stu-id="15b05-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15b05-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="15b05-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15b05-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="15b05-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b05-119">Требования</span><span class="sxs-lookup"><span data-stu-id="15b05-119">Requirements</span></span>  
 <span data-ttu-id="15b05-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15b05-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b05-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15b05-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15b05-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15b05-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15b05-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b05-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b05-124">См. также</span><span class="sxs-lookup"><span data-stu-id="15b05-124">See also</span></span>

- [<span data-ttu-id="15b05-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="15b05-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
