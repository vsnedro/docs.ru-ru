---
title: Перечисление COR_PRF_MISC
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: 7b8f2845589a8372f62c95ef1a82eae3ed602c1f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500836"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="5d38c-102">Перечисление COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="5d38c-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="5d38c-103">Содержит постоянные значения, которые указывают специальные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="5d38c-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d38c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d38c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="5d38c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5d38c-105">Members</span></span>  
  
|<span data-ttu-id="5d38c-106">Член</span><span class="sxs-lookup"><span data-stu-id="5d38c-106">Member</span></span>|<span data-ttu-id="5d38c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5d38c-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="5d38c-108">Идентификатор по умолчанию, используемый [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) для модуля, который еще не присоединен к сборке.</span><span class="sxs-lookup"><span data-stu-id="5d38c-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="5d38c-109">Идентификатор класса по умолчанию для глобальных констант, которые не принадлежат классу.</span><span class="sxs-lookup"><span data-stu-id="5d38c-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="5d38c-110">Идентификатор модуля по умолчанию для глобальных объектов, которые не принадлежат модулю.</span><span class="sxs-lookup"><span data-stu-id="5d38c-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d38c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5d38c-111">Requirements</span></span>  
 <span data-ttu-id="5d38c-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d38c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d38c-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d38c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d38c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d38c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d38c-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d38c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d38c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5d38c-116">See also</span></span>

- [<span data-ttu-id="5d38c-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="5d38c-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
