---
title: Интерфейс ICorDebugRegisterSet2
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: c04bb3a7584fcb783af929e87713dbec67ad705f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712330"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="370cf-102">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="370cf-102">ICorDebugRegisterSet2 Interface</span></span>

<span data-ttu-id="370cf-103">Расширяет возможности интерфейса [ICorDebugRegisterSet](icordebugregisterset-interface.md) для аппаратных платформ, имеющих более 64 регистров.</span><span class="sxs-lookup"><span data-stu-id="370cf-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="370cf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="370cf-104">Methods</span></span>  
  
|<span data-ttu-id="370cf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="370cf-105">Method</span></span>|<span data-ttu-id="370cf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="370cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="370cf-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="370cf-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="370cf-108">Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.</span><span class="sxs-lookup"><span data-stu-id="370cf-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="370cf-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="370cf-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="370cf-110">Возвращает массив байтов, предоставляющий битовую карту доступных регистров.</span><span class="sxs-lookup"><span data-stu-id="370cf-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="370cf-111">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="370cf-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="370cf-112">Не реализовано в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="370cf-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="370cf-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="370cf-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="370cf-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="370cf-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="370cf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="370cf-115">Requirements</span></span>  

 <span data-ttu-id="370cf-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="370cf-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="370cf-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="370cf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="370cf-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="370cf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="370cf-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="370cf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="370cf-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="370cf-120">See also</span></span>

- [<span data-ttu-id="370cf-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="370cf-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="370cf-122">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="370cf-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
