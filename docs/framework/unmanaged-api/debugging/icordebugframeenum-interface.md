---
title: Интерфейс ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
ms.openlocfilehash: 4bc8d56bf116cd64e3e1c5d2238e557784c56711
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209608"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="173d4-102">Интерфейс ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="173d4-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="173d4-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="173d4-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="173d4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="173d4-104">Methods</span></span>  
  
|<span data-ttu-id="173d4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="173d4-105">Method</span></span>|<span data-ttu-id="173d4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="173d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="173d4-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="173d4-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="173d4-108">Возвращает указанное количество `ICorDebugFrame` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="173d4-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="173d4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="173d4-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="173d4-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="173d4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="173d4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="173d4-111">Requirements</span></span>  
 <span data-ttu-id="173d4-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="173d4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="173d4-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="173d4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="173d4-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="173d4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="173d4-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="173d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173d4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="173d4-116">See also</span></span>

- [<span data-ttu-id="173d4-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="173d4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
