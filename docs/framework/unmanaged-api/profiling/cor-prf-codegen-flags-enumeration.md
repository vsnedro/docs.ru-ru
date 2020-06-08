---
title: Перечисление COR_PRF_CODEGEN_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
ms.openlocfilehash: c2c7ae7a8930949c79b5e24e2da75f3b4649e7f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500992"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="201c2-102">Перечисление COR_PRF_CODEGEN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="201c2-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="201c2-103">Определяет флаги создания кода, которые можно задать с помощью метода [икорпрофилерфунктионконтрол:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="201c2-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="201c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="201c2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="201c2-105">Участники</span><span class="sxs-lookup"><span data-stu-id="201c2-105">Members</span></span>  
  
|<span data-ttu-id="201c2-106">Член</span><span class="sxs-lookup"><span data-stu-id="201c2-106">Member</span></span>|<span data-ttu-id="201c2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="201c2-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="201c2-108">Никакие функции не будут встроены в текст этой функции.</span><span class="sxs-lookup"><span data-stu-id="201c2-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="201c2-109">Однако сама функция может быть встроена в ее вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="201c2-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="201c2-110">Для текста этой функции будут отключены все оптимизации.</span><span class="sxs-lookup"><span data-stu-id="201c2-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="201c2-111">Однако сама функция по-прежнему может быть встроена в ее вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="201c2-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="201c2-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="201c2-112">Remarks</span></span>  
 <span data-ttu-id="201c2-113">`COR_PRF_CODEGEN_FLAGS`Перечисление используется методом [икорпрофилерфунктионконтрол:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) , чтобы позволить профилировщику управлять созданием кода для JIT-перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="201c2-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="201c2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="201c2-114">Requirements</span></span>  
 <span data-ttu-id="201c2-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="201c2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="201c2-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="201c2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="201c2-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="201c2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="201c2-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="201c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="201c2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="201c2-119">See also</span></span>

- [<span data-ttu-id="201c2-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="201c2-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
