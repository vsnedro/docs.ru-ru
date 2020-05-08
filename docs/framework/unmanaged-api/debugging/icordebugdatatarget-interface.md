---
title: Интерфейс ICorDebugDataTarget
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
ms.openlocfilehash: 54272dd18a12715bab58ec1b1a4c1dc00e4bf12b
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976529"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="3368a-102">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="3368a-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="3368a-103">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="3368a-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3368a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3368a-104">Methods</span></span>  
  
|<span data-ttu-id="3368a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3368a-105">Method</span></span>|<span data-ttu-id="3368a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3368a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3368a-107">Метод GetPlatform</span><span class="sxs-lookup"><span data-stu-id="3368a-107">GetPlatform Method</span></span>](icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="3368a-108">Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="3368a-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="3368a-109">Метод ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="3368a-109">ReadVirtual Method</span></span>](icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="3368a-110">Возвращает блок непрерывной памяти, начиная с указанного адреса, и возвращает его в указанном буфере.</span><span class="sxs-lookup"><span data-stu-id="3368a-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="3368a-111">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3368a-111">GetThreadContext Method</span></span>](icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="3368a-112">Запрашивает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="3368a-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3368a-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3368a-113">Remarks</span></span>  
 <span data-ttu-id="3368a-114">`ICorDebugDataTarget`и его методы имеют следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="3368a-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="3368a-115">Службы отладки вызывают методы этого интерфейса для доступа к памяти и другим данным в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="3368a-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="3368a-116">Клиент отладчика должен реализовать этот интерфейс в соответствии с конкретным целевым объектом (например, в реальном процессе или дампе памяти).</span><span class="sxs-lookup"><span data-stu-id="3368a-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="3368a-117">`ICorDebugDataTarget` Методы могут вызываться только в методах, реализованных в других `ICorDebug*` интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="3368a-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="3368a-118">Это гарантирует, что клиент отладчика будет контролировать, в каком потоке он вызывается, и когда.</span><span class="sxs-lookup"><span data-stu-id="3368a-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="3368a-119">`ICorDebugDataTarget` Реализация всегда должна возвращать актуальные сведения о целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="3368a-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="3368a-120">Целевой процесс должен быть остановлен и не изменяется каким-либо образом при `ICorDebug*` вызове интерфейсов `ICorDebugDataTarget` (и, следовательно, методов).</span><span class="sxs-lookup"><span data-stu-id="3368a-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="3368a-121">Если целевой объект является динамическим процессом и изменяется его состояние, метод [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) необходимо вызвать снова, чтобы предоставить экземпляр ICorDebugProcess для замены.</span><span class="sxs-lookup"><span data-stu-id="3368a-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3368a-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3368a-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3368a-123">Требования</span><span class="sxs-lookup"><span data-stu-id="3368a-123">Requirements</span></span>  
 <span data-ttu-id="3368a-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3368a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3368a-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3368a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3368a-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3368a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3368a-127">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3368a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3368a-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3368a-128">See also</span></span>

- [<span data-ttu-id="3368a-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3368a-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3368a-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="3368a-130">Debugging</span></span>](index.md)
