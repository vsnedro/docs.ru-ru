---
title: Структура COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: 5feda2ce6dc97576d0b1d4f16ca2b9dd5f3fb05e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718567"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="3dbd8-102">Структура COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="3dbd8-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>

<span data-ttu-id="3dbd8-103">Представляет аргументы функции слева направо.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dbd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3dbd8-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3dbd8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3dbd8-105">Members</span></span>  
  
|<span data-ttu-id="3dbd8-106">Член</span><span class="sxs-lookup"><span data-stu-id="3dbd8-106">Member</span></span>|<span data-ttu-id="3dbd8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3dbd8-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="3dbd8-108">Число блоков аргументов.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-108">The number of blocks of arguments.</span></span> <span data-ttu-id="3dbd8-109">То есть это значение равно количеству структур [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) в `ranges` массиве.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="3dbd8-110">Общий размер всех аргументов.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-110">The total size of all arguments.</span></span> <span data-ttu-id="3dbd8-111">Иными словами, это значение является суммой длин аргументов.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="3dbd8-112">Массив `COR_PRF_FUNCTION_ARGUMENT_RANGE` структур, каждый из которых представляет один блок аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dbd8-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3dbd8-113">Remarks</span></span>  

 <span data-ttu-id="3dbd8-114">У функции может быть несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-114">A function may have many arguments.</span></span> <span data-ttu-id="3dbd8-115">Эти аргументы могут не храниться непрерывно в памяти.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="3dbd8-116">У вас может быть блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и последний блок одного аргумента в другом месте.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="3dbd8-117">Все эти аргументы используются для одной и той же функции. они просто хранятся в разных местах.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="3dbd8-118">`COR_PRF_FUNCTION_ARGUMENT_INFO`Структура представляет все аргументы одной функции.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="3dbd8-119">Он использует массив для ссылки на все блоки аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="3dbd8-120">Таким образом, для одной функции имеется одна `COR_PRF_FUNCTION_ARGUMENT_INFO` структура, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE` структур, каждая из которых указывает на один или несколько аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="3dbd8-121">Аргументы, хранимые в регистрах, загружаются в память для построения структур.</span><span class="sxs-lookup"><span data-stu-id="3dbd8-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dbd8-122">Требования</span><span class="sxs-lookup"><span data-stu-id="3dbd8-122">Requirements</span></span>  

 <span data-ttu-id="3dbd8-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dbd8-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dbd8-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="3dbd8-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3dbd8-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dbd8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dbd8-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dbd8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbd8-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3dbd8-127">See also</span></span>

- [<span data-ttu-id="3dbd8-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="3dbd8-128">Profiling Structures</span></span>](profiling-structures.md)
