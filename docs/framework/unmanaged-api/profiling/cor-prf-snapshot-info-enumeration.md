---
title: Перечисление COR_PRF_SNAPSHOT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 5290db008bfe5727ed5899c2ed6f7e41ae9a353a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716360"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="2d655-102">Перечисление COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="2d655-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>

<span data-ttu-id="2d655-103">Указывает объем данных, которые необходимо передать обратно с помощью моментального снимка стека при каждом вызове функции [стаккснапшоткаллбакк](stacksnapshotcallback-function.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="2d655-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d655-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d655-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="2d655-105">Члены</span><span class="sxs-lookup"><span data-stu-id="2d655-105">Members</span></span>  
  
|<span data-ttu-id="2d655-106">Элементы</span><span class="sxs-lookup"><span data-stu-id="2d655-106">Members</span></span>|<span data-ttu-id="2d655-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2d655-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="2d655-108">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, кроме `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="2d655-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="2d655-109">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, включая `context` параметр.</span><span class="sxs-lookup"><span data-stu-id="2d655-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="2d655-110">Указывает, что будет использоваться более простой и альтернативный алгоритм анализа стека.</span><span class="sxs-lookup"><span data-stu-id="2d655-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d655-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2d655-111">Remarks</span></span>  

 <span data-ttu-id="2d655-112">Значения, предоставляемые `COR_PRF_SNAPSHOT_INFO` перечислением, передаются в качестве параметров в метод [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2d655-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d655-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2d655-113">Requirements</span></span>  

 <span data-ttu-id="2d655-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d655-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d655-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d655-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d655-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d655-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d655-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d655-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d655-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2d655-118">See also</span></span>

- [<span data-ttu-id="2d655-119">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="2d655-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="2d655-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="2d655-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
