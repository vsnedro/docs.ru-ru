---
title: Интерфейс ICorDebugValueEnum
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: e3934cbce76df3997fa07d8fa3a99bd8ddab09a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684347"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="22b92-102">Интерфейс ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="22b92-102">ICorDebugValueEnum Interface</span></span>

<span data-ttu-id="22b92-103">Реализует методы "ICorDebugEnum" и перечисляет массивы "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="22b92-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22b92-104">Методы</span><span class="sxs-lookup"><span data-stu-id="22b92-104">Methods</span></span>  
  
|<span data-ttu-id="22b92-105">Метод</span><span class="sxs-lookup"><span data-stu-id="22b92-105">Method</span></span>|<span data-ttu-id="22b92-106">Описание</span><span class="sxs-lookup"><span data-stu-id="22b92-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22b92-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="22b92-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="22b92-108">Возвращает указанное количество `ICorDebugValue` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="22b92-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22b92-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="22b92-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22b92-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="22b92-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22b92-111">Требования</span><span class="sxs-lookup"><span data-stu-id="22b92-111">Requirements</span></span>  

 <span data-ttu-id="22b92-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22b92-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22b92-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22b92-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22b92-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22b92-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22b92-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22b92-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b92-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="22b92-116">See also</span></span>

- [<span data-ttu-id="22b92-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="22b92-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
