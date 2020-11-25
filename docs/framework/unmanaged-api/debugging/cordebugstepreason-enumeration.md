---
title: Перечисление CorDebugStepReason
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 50903b3737c0fc63eda2b1190e4c3d961ce3ae7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726045"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="2947b-102">Перечисление CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="2947b-102">CorDebugStepReason Enumeration</span></span>

<span data-ttu-id="2947b-103">Указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="2947b-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2947b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2947b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="2947b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="2947b-105">Members</span></span>  
  
|<span data-ttu-id="2947b-106">Член</span><span class="sxs-lookup"><span data-stu-id="2947b-106">Member</span></span>|<span data-ttu-id="2947b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2947b-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="2947b-108">Пошаговое завершение нормального выполнения в одной и той же функции.</span><span class="sxs-lookup"><span data-stu-id="2947b-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="2947b-109">Пошаговое продолжение обычно после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="2947b-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="2947b-110">Пошаговое продолжение обычно в начале вновь вызванной функции.</span><span class="sxs-lookup"><span data-stu-id="2947b-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="2947b-111">Было создано исключение, и управление было передано в фильтр исключений.</span><span class="sxs-lookup"><span data-stu-id="2947b-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="2947b-112">Было создано исключение, а Управление было передано обработчику исключений.</span><span class="sxs-lookup"><span data-stu-id="2947b-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="2947b-113">Элемент управления передан перехватчику.</span><span class="sxs-lookup"><span data-stu-id="2947b-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="2947b-114">Поток завершил работу до завершения шага.</span><span class="sxs-lookup"><span data-stu-id="2947b-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2947b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2947b-115">Requirements</span></span>  

 <span data-ttu-id="2947b-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2947b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2947b-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2947b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2947b-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2947b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2947b-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2947b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2947b-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2947b-120">See also</span></span>

- [<span data-ttu-id="2947b-121">Метод StepComplete</span><span class="sxs-lookup"><span data-stu-id="2947b-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="2947b-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="2947b-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
