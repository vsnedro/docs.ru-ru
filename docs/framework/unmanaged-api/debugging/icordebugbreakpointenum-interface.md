---
title: Интерфейс ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: 97e06a2f20dcc2bb3815b98ba29ff230e37ff29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730166"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="b6aa6-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="b6aa6-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="b6aa6-103">Реализует методы ICorDebugEnum и перечисляет Икордебугбреакпоинт массивы.</span><span class="sxs-lookup"><span data-stu-id="b6aa6-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6aa6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b6aa6-104">Methods</span></span>  
  
|<span data-ttu-id="b6aa6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b6aa6-105">Method</span></span>|<span data-ttu-id="b6aa6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6aa6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6aa6-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="b6aa6-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="b6aa6-108">Возвращает указанное количество `ICorDebugBreakpoint` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="b6aa6-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6aa6-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b6aa6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6aa6-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b6aa6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6aa6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b6aa6-111">Requirements</span></span>  

 <span data-ttu-id="b6aa6-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6aa6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6aa6-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6aa6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6aa6-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6aa6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6aa6-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6aa6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6aa6-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b6aa6-116">See also</span></span>

- [<span data-ttu-id="b6aa6-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b6aa6-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
