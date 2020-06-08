---
title: Перечисление COR_PRF_JIT_CACHE
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: d19d7ed2262db6d3c6e7f15db0e96da52f86db4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500862"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="6c805-102">Перечисление COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="6c805-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="6c805-103">Указывает результат кэшированной функции поиска.</span><span class="sxs-lookup"><span data-stu-id="6c805-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c805-104">`COR_PRF_CACHED_FUNCTION_FOUND`имеет нулевое значение, поэтому `COR_PRF_JIT_CACHE` не может использоваться в качестве логического суррогата.</span><span class="sxs-lookup"><span data-stu-id="6c805-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c805-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c805-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="6c805-106">Участники</span><span class="sxs-lookup"><span data-stu-id="6c805-106">Members</span></span>  
  
|<span data-ttu-id="6c805-107">Член</span><span class="sxs-lookup"><span data-stu-id="6c805-107">Member</span></span>|<span data-ttu-id="6c805-108">Описание</span><span class="sxs-lookup"><span data-stu-id="6c805-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="6c805-109">Поиск обнаружил функцию.</span><span class="sxs-lookup"><span data-stu-id="6c805-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="6c805-110">Поиск не нашел функцию.</span><span class="sxs-lookup"><span data-stu-id="6c805-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c805-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6c805-111">Requirements</span></span>  
 <span data-ttu-id="6c805-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c805-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c805-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c805-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c805-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c805-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c805-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c805-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c805-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6c805-116">See also</span></span>

- [<span data-ttu-id="6c805-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="6c805-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
