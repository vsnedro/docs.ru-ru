---
title: Интерфейс ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: 82a7689bb1848d89f5dee4482d8dc7685c9c5b5c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378339"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="dd11d-102">Интерфейс ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="dd11d-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="dd11d-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="dd11d-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd11d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="dd11d-104">Methods</span></span>  
  
|<span data-ttu-id="dd11d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="dd11d-105">Method</span></span>|<span data-ttu-id="dd11d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="dd11d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd11d-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="dd11d-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="dd11d-108">Возвращает указанное количество `ICorDebugThread` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="dd11d-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd11d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd11d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd11d-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="dd11d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd11d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dd11d-111">Requirements</span></span>  
 <span data-ttu-id="dd11d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd11d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd11d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd11d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd11d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd11d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd11d-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd11d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd11d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dd11d-116">See also</span></span>

- [<span data-ttu-id="dd11d-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dd11d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
