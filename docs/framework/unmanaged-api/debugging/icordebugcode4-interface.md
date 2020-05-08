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
ms.openlocfilehash: 870ac1e62363493989fe638483ea474d648c8c69
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893310"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="0d0d6-102">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="0d0d6-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="0d0d6-103">Предоставляет метод, позволяющий отладчику перечислить локальные переменные и аргументы в функции.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d0d6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0d0d6-104">Methods</span></span>  
  
|<span data-ttu-id="0d0d6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0d0d6-105">Method</span></span>|<span data-ttu-id="0d0d6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0d0d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d0d6-107">Метод EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="0d0d6-107">EnumerateVariableHomes Method</span></span>](icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="0d0d6-108">Возвращает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d0d6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d0d6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d0d6-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0d0d6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d0d6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0d0d6-111">Requirements</span></span>  
 <span data-ttu-id="0d0d6-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d0d6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d0d6-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d0d6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d0d6-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d0d6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d0d6-115">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0d6-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d0d6-116">See also</span></span>

- [<span data-ttu-id="0d0d6-117">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="0d0d6-117">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="0d0d6-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0d0d6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
