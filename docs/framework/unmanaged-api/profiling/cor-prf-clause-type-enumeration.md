---
title: Перечисление COR_PRF_CLAUSE_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
ms.openlocfilehash: a308017dc80dd973cbf108ba9df824193775f5ff
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501057"
---
# <a name="cor_prf_clause_type-enumeration"></a><span data-ttu-id="45c5e-102">Перечисление COR_PRF_CLAUSE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45c5e-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="45c5e-103">Указывает тип предложения исключения, код которого был только что введен или удален.</span><span class="sxs-lookup"><span data-stu-id="45c5e-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45c5e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45c5e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="45c5e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="45c5e-105">Members</span></span>  
  
|<span data-ttu-id="45c5e-106">Член</span><span class="sxs-lookup"><span data-stu-id="45c5e-106">Member</span></span>|<span data-ttu-id="45c5e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="45c5e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="45c5e-108">Недопустимое предложение исключения.</span><span class="sxs-lookup"><span data-stu-id="45c5e-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="45c5e-109">Предложение Exception является критерием фильтра.</span><span class="sxs-lookup"><span data-stu-id="45c5e-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="45c5e-110">Предложение Exception является `catch` оператором.</span><span class="sxs-lookup"><span data-stu-id="45c5e-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="45c5e-111">Предложение Exception является `finally` оператором.</span><span class="sxs-lookup"><span data-stu-id="45c5e-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45c5e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="45c5e-112">Requirements</span></span>  
 <span data-ttu-id="45c5e-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c5e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45c5e-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45c5e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45c5e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45c5e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45c5e-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45c5e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c5e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="45c5e-117">See also</span></span>

- [<span data-ttu-id="45c5e-118">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="45c5e-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
