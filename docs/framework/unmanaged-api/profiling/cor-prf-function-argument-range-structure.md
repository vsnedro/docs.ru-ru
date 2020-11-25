---
title: Структура COR_PRF_FUNCTION_ARGUMENT_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: 028395b1c8677d07d4a6481740ecdc7ebb48c180
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718531"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="6583c-102">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="6583c-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>

<span data-ttu-id="6583c-103">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="6583c-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6583c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6583c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="6583c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6583c-105">Members</span></span>  
  
|<span data-ttu-id="6583c-106">Элементы</span><span class="sxs-lookup"><span data-stu-id="6583c-106">Members</span></span>|<span data-ttu-id="6583c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6583c-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="6583c-108">Начальный адрес блока.</span><span class="sxs-lookup"><span data-stu-id="6583c-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="6583c-109">Длина непрерывного блока.</span><span class="sxs-lookup"><span data-stu-id="6583c-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6583c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6583c-110">Requirements</span></span>  

 <span data-ttu-id="6583c-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6583c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6583c-112">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="6583c-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6583c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6583c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6583c-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6583c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6583c-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6583c-115">See also</span></span>

- [<span data-ttu-id="6583c-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="6583c-116">Profiling Structures</span></span>](profiling-structures.md)
