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
ms.openlocfilehash: 288d7bfdf18be5cef032227c537032966fa68df4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795707"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="b0fe9-102">Перечисление CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="b0fe9-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="b0fe9-103">Указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0fe9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0fe9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b0fe9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b0fe9-105">Members</span></span>  
  
|<span data-ttu-id="b0fe9-106">Участник</span><span class="sxs-lookup"><span data-stu-id="b0fe9-106">Member</span></span>|<span data-ttu-id="b0fe9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b0fe9-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="b0fe9-108">Пошаговое завершение нормального выполнения в одной и той же функции.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="b0fe9-109">Пошаговое продолжение обычно после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="b0fe9-110">Пошаговое продолжение обычно в начале вновь вызванной функции.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="b0fe9-111">Было создано исключение, и управление было передано в фильтр исключений.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="b0fe9-112">Было создано исключение, а Управление было передано обработчику исключений.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="b0fe9-113">Элемент управления передан перехватчику.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="b0fe9-114">Поток завершил работу до завершения шага.</span><span class="sxs-lookup"><span data-stu-id="b0fe9-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0fe9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b0fe9-115">Requirements</span></span>  
 <span data-ttu-id="b0fe9-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0fe9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0fe9-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0fe9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0fe9-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0fe9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0fe9-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0fe9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fe9-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b0fe9-120">See also</span></span>

- [<span data-ttu-id="b0fe9-121">Метод StepComplete</span><span class="sxs-lookup"><span data-stu-id="b0fe9-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="b0fe9-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b0fe9-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
