---
title: Перечисление COR_PRF_FINALIZER_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: b273faafd7abb86ace58bb5c24473406af3ce20e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500979"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="fed86-102">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fed86-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="fed86-103">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="fed86-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fed86-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="fed86-105">Участники</span><span class="sxs-lookup"><span data-stu-id="fed86-105">Members</span></span>  
  
|<span data-ttu-id="fed86-106">Член</span><span class="sxs-lookup"><span data-stu-id="fed86-106">Member</span></span>|<span data-ttu-id="fed86-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fed86-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="fed86-108">Метод завершения является критическим.</span><span class="sxs-lookup"><span data-stu-id="fed86-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fed86-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fed86-109">Remarks</span></span>  
 <span data-ttu-id="fed86-110">`COR_PRF_FINALIZER_FLAGS`Перечисление используется методом [ICorProfilerCallback2:: финализеаблеобжекткуеуед](icorprofilercallback2-finalizeableobjectqueued-method.md) для описания метода завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="fed86-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed86-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fed86-111">Requirements</span></span>  
 <span data-ttu-id="fed86-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fed86-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed86-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fed86-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fed86-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed86-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed86-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed86-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fed86-116">See also</span></span>

- [<span data-ttu-id="fed86-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="fed86-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
