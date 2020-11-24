---
title: Структура COR_PRF_EX_CLAUSE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: e8dd9f21803021975f4651ba3e6e5f4d3da0ea82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675000"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="192c0-102">Структура COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="192c0-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>

<span data-ttu-id="192c0-103">Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="192c0-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="192c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="192c0-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="192c0-105">Члены</span><span class="sxs-lookup"><span data-stu-id="192c0-105">Members</span></span>  
  
|<span data-ttu-id="192c0-106">Член</span><span class="sxs-lookup"><span data-stu-id="192c0-106">Member</span></span>|<span data-ttu-id="192c0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="192c0-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="192c0-108">Значение перечисления [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) , указывающее тип предложения исключения, введенного или левого кода.</span><span class="sxs-lookup"><span data-stu-id="192c0-108">A value of the [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="192c0-109">Собственная точка входа обработчика предложения, например, содержимое регистра x86 EIP.</span><span class="sxs-lookup"><span data-stu-id="192c0-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="192c0-110">Указатель на логический кадр для обработчика предложения, например содержимое регистра x86 EBP.</span><span class="sxs-lookup"><span data-stu-id="192c0-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="192c0-111">Указатель на теневой стек.</span><span class="sxs-lookup"><span data-stu-id="192c0-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="192c0-112">Это значение является содержимым регистра BSP и применяется только к версии IA64.</span><span class="sxs-lookup"><span data-stu-id="192c0-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="192c0-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="192c0-113">Remarks</span></span>  

 <span data-ttu-id="192c0-114">При получении уведомления об исключении можно использовать [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) для получения сведений о собственном адресе и кадре для предложения исключения ( `catch` / `finally` /Filter), которое должно быть запущено или только что было запущено.</span><span class="sxs-lookup"><span data-stu-id="192c0-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="192c0-115">Выполнение предложения исключения включает следующие обратные вызовы из среды CLR:</span><span class="sxs-lookup"><span data-stu-id="192c0-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="192c0-116">ICorProfilerCallback:: Ексцептионкатчерентер</span><span class="sxs-lookup"><span data-stu-id="192c0-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="192c0-117">ICorProfilerCallback:: Ексцептионунвиндфиналлентер</span><span class="sxs-lookup"><span data-stu-id="192c0-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="192c0-118">ICorProfilerCallback:: Ексцептионсеарчфилтерентер</span><span class="sxs-lookup"><span data-stu-id="192c0-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="192c0-119">ICorProfilerCallback:: Ексцептионкатчерлеаве</span><span class="sxs-lookup"><span data-stu-id="192c0-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="192c0-120">ICorProfilerCallback:: Exceptionunwindfinallyleave-</span><span class="sxs-lookup"><span data-stu-id="192c0-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="192c0-121">ICorProfilerCallback:: Ексцептионсеарчфилтерлеаве</span><span class="sxs-lookup"><span data-stu-id="192c0-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="192c0-122">Требования</span><span class="sxs-lookup"><span data-stu-id="192c0-122">Requirements</span></span>  

 <span data-ttu-id="192c0-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="192c0-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="192c0-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="192c0-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="192c0-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="192c0-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="192c0-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="192c0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192c0-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="192c0-127">See also</span></span>

- [<span data-ttu-id="192c0-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="192c0-128">Profiling Structures</span></span>](profiling-structures.md)
