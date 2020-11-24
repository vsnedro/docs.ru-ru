---
title: Структура COR_PRF_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 1da8f414ccf0c1eed3ec7dde842dd381440a3fa9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674961"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="84840-102">Структура COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="84840-102">COR_PRF_FUNCTION Structure</span></span>

<span data-ttu-id="84840-103">Выдает уникальное представление функции, объединяя ее идентификатор с идентификатором перекомпилированной версии этой функции.</span><span class="sxs-lookup"><span data-stu-id="84840-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84840-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84840-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="84840-105">Члены</span><span class="sxs-lookup"><span data-stu-id="84840-105">Members</span></span>  
  
|<span data-ttu-id="84840-106">Член</span><span class="sxs-lookup"><span data-stu-id="84840-106">Member</span></span>|<span data-ttu-id="84840-107">Описание</span><span class="sxs-lookup"><span data-stu-id="84840-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="84840-108">Идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="84840-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="84840-109">Идентификатор перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="84840-109">The ID of the recompiled function.</span></span> <span data-ttu-id="84840-110">Значение 0 (ноль) представляет исходную версию функции.</span><span class="sxs-lookup"><span data-stu-id="84840-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84840-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="84840-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84840-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84840-112">Requirements</span></span>  

 <span data-ttu-id="84840-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84840-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84840-114">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="84840-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="84840-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84840-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84840-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84840-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84840-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84840-117">See also</span></span>

- [<span data-ttu-id="84840-118">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="84840-118">Profiling Structures</span></span>](profiling-structures.md)
