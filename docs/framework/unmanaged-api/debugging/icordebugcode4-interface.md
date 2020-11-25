---
title: Интерфейс ICorDebugCode4
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
ms.openlocfilehash: 8a373afdf41590ec44a7cbac7360719a12faa82e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720728"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="3d790-102">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="3d790-102">ICorDebugCode4 Interface</span></span>

<span data-ttu-id="3d790-103">Предоставляет метод, позволяющий отладчику перечислить локальные переменные и аргументы в функции.</span><span class="sxs-lookup"><span data-stu-id="3d790-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d790-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3d790-104">Methods</span></span>  
  
|<span data-ttu-id="3d790-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3d790-105">Method</span></span>|<span data-ttu-id="3d790-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3d790-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d790-107">Метод EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="3d790-107">EnumerateVariableHomes Method</span></span>](icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="3d790-108">Возвращает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="3d790-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d790-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3d790-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d790-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3d790-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d790-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3d790-111">Requirements</span></span>  

 <span data-ttu-id="3d790-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d790-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d790-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d790-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d790-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d790-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d790-115">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d790-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d790-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d790-116">See also</span></span>

- [<span data-ttu-id="3d790-117">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="3d790-117">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="3d790-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3d790-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
