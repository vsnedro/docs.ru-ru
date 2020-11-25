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
ms.openlocfilehash: 747313f217092652d5a9404fbf81383fa0828ee9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696665"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="1a98a-102">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="1a98a-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>

<span data-ttu-id="1a98a-103">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="1a98a-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a98a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a98a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="1a98a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1a98a-105">Members</span></span>  
  
|<span data-ttu-id="1a98a-106">Член</span><span class="sxs-lookup"><span data-stu-id="1a98a-106">Member</span></span>|<span data-ttu-id="1a98a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1a98a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="1a98a-108">Переход происходит из-за вызова функции.</span><span class="sxs-lookup"><span data-stu-id="1a98a-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="1a98a-109">Переход происходит из-за возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="1a98a-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a98a-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1a98a-110">Remarks</span></span>  

 <span data-ttu-id="1a98a-111">Когда происходит переход, профилировщик получает обратный вызов [ICorProfilerCallback:: манажедтаунманажедтранситион](icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback:: унманажедтоманажедтранситион](icorprofilercallback-unmanagedtomanagedtransition-method.md) , который предоставляет значение `COR_PRF_TRANSITION_REASON` перечисления для указания причины перехода.</span><span class="sxs-lookup"><span data-stu-id="1a98a-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a98a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1a98a-112">Requirements</span></span>  

 <span data-ttu-id="1a98a-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a98a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a98a-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a98a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a98a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a98a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a98a-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a98a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
