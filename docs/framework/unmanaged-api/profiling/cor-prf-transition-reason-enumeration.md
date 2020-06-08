---
title: Перечисление COR_PRF_TRANSITION_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: e890c62a54654e86bb4a825613807efe142c8d5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500745"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="5947c-102">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="5947c-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="5947c-103">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="5947c-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5947c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5947c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="5947c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5947c-105">Members</span></span>  
  
|<span data-ttu-id="5947c-106">Член</span><span class="sxs-lookup"><span data-stu-id="5947c-106">Member</span></span>|<span data-ttu-id="5947c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5947c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="5947c-108">Переход происходит из-за вызова функции.</span><span class="sxs-lookup"><span data-stu-id="5947c-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="5947c-109">Переход происходит из-за возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="5947c-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5947c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5947c-110">Remarks</span></span>  
 <span data-ttu-id="5947c-111">Когда происходит переход, профилировщик получает обратный вызов [ICorProfilerCallback:: манажедтаунманажедтранситион](icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback:: унманажедтоманажедтранситион](icorprofilercallback-unmanagedtomanagedtransition-method.md) , который предоставляет значение `COR_PRF_TRANSITION_REASON` перечисления для указания причины перехода.</span><span class="sxs-lookup"><span data-stu-id="5947c-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5947c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5947c-112">Requirements</span></span>  
 <span data-ttu-id="5947c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5947c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5947c-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5947c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5947c-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5947c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5947c-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5947c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
