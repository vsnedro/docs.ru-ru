---
title: Интерфейс ICorDebugEnum
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: 7575be3f5074243b251c80b8dd5bdbb12e5d50fd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976334"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="09332-102">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="09332-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="09332-103">Служит абстрактным базовым интерфейсом для перечислителей, используемых приложением отладки.</span><span class="sxs-lookup"><span data-stu-id="09332-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09332-104">Методы</span><span class="sxs-lookup"><span data-stu-id="09332-104">Methods</span></span>  
  
|<span data-ttu-id="09332-105">Метод</span><span class="sxs-lookup"><span data-stu-id="09332-105">Method</span></span>|<span data-ttu-id="09332-106">Описание</span><span class="sxs-lookup"><span data-stu-id="09332-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09332-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="09332-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="09332-108">Создает копию данного объекта `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="09332-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="09332-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="09332-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="09332-110">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="09332-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="09332-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="09332-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="09332-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="09332-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="09332-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="09332-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="09332-114">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="09332-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09332-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="09332-115">Remarks</span></span>  
 <span data-ttu-id="09332-116">Следующие перечислители являются производными `ICorDebugEnum`от:</span><span class="sxs-lookup"><span data-stu-id="09332-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="09332-117">"Икордебугаппдомаиненум"</span><span class="sxs-lookup"><span data-stu-id="09332-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="09332-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="09332-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="09332-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="09332-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="09332-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="09332-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="09332-121">"Икордебугчаиненум"</span><span class="sxs-lookup"><span data-stu-id="09332-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="09332-122">"Икордебугкодинум"</span><span class="sxs-lookup"><span data-stu-id="09332-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="09332-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="09332-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="09332-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="09332-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="09332-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="09332-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="09332-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="09332-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="09332-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="09332-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="09332-128">икордебугхеапенум</span><span class="sxs-lookup"><span data-stu-id="09332-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="09332-129">икордебугхеапсегментенум</span><span class="sxs-lookup"><span data-stu-id="09332-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="09332-130">"Икордебугмодулинум"</span><span class="sxs-lookup"><span data-stu-id="09332-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="09332-131">"Икордебугобжектенум"</span><span class="sxs-lookup"><span data-stu-id="09332-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="09332-132">"Икордебугпроцессенум"</span><span class="sxs-lookup"><span data-stu-id="09332-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="09332-133">"Икордебугстепперенум"</span><span class="sxs-lookup"><span data-stu-id="09332-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="09332-134">"Икордебугсреаденум"</span><span class="sxs-lookup"><span data-stu-id="09332-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="09332-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="09332-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="09332-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="09332-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="09332-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="09332-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="09332-138">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="09332-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09332-139">Требования</span><span class="sxs-lookup"><span data-stu-id="09332-139">Requirements</span></span>  
 <span data-ttu-id="09332-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09332-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09332-141">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09332-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09332-142">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09332-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09332-143">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09332-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09332-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="09332-144">See also</span></span>

- [<span data-ttu-id="09332-145">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="09332-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
