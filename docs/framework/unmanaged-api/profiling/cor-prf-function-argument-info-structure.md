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
ms.openlocfilehash: 9fca75ae59b95a226b51768b3e1bfb220d9926f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500970"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="dedc3-102">Структура COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="dedc3-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="dedc3-103">Представляет аргументы функции слева направо.</span><span class="sxs-lookup"><span data-stu-id="dedc3-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dedc3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dedc3-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="dedc3-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dedc3-105">Members</span></span>  
  
|<span data-ttu-id="dedc3-106">Член</span><span class="sxs-lookup"><span data-stu-id="dedc3-106">Member</span></span>|<span data-ttu-id="dedc3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dedc3-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="dedc3-108">Число блоков аргументов.</span><span class="sxs-lookup"><span data-stu-id="dedc3-108">The number of blocks of arguments.</span></span> <span data-ttu-id="dedc3-109">То есть это значение равно количеству структур [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) в `ranges` массиве.</span><span class="sxs-lookup"><span data-stu-id="dedc3-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="dedc3-110">Общий размер всех аргументов.</span><span class="sxs-lookup"><span data-stu-id="dedc3-110">The total size of all arguments.</span></span> <span data-ttu-id="dedc3-111">Иными словами, это значение является суммой длин аргументов.</span><span class="sxs-lookup"><span data-stu-id="dedc3-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="dedc3-112">Массив `COR_PRF_FUNCTION_ARGUMENT_RANGE` структур, каждый из которых представляет один блок аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="dedc3-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dedc3-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="dedc3-113">Remarks</span></span>  
 <span data-ttu-id="dedc3-114">У функции может быть несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="dedc3-114">A function may have many arguments.</span></span> <span data-ttu-id="dedc3-115">Эти аргументы могут не храниться непрерывно в памяти.</span><span class="sxs-lookup"><span data-stu-id="dedc3-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="dedc3-116">У вас может быть блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и последний блок одного аргумента в другом месте.</span><span class="sxs-lookup"><span data-stu-id="dedc3-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="dedc3-117">Все эти аргументы используются для одной и той же функции. они просто хранятся в разных местах.</span><span class="sxs-lookup"><span data-stu-id="dedc3-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="dedc3-118">`COR_PRF_FUNCTION_ARGUMENT_INFO`Структура представляет все аргументы одной функции.</span><span class="sxs-lookup"><span data-stu-id="dedc3-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="dedc3-119">Он использует массив для ссылки на все блоки аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="dedc3-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="dedc3-120">Таким образом, для одной функции имеется одна `COR_PRF_FUNCTION_ARGUMENT_INFO` структура, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE` структур, каждая из которых указывает на один или несколько аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="dedc3-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="dedc3-121">Аргументы, хранимые в регистрах, загружаются в память для построения структур.</span><span class="sxs-lookup"><span data-stu-id="dedc3-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dedc3-122">Требования</span><span class="sxs-lookup"><span data-stu-id="dedc3-122">Requirements</span></span>  
 <span data-ttu-id="dedc3-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dedc3-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dedc3-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="dedc3-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="dedc3-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dedc3-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dedc3-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dedc3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dedc3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="dedc3-127">See also</span></span>

- [<span data-ttu-id="dedc3-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="dedc3-128">Profiling Structures</span></span>](profiling-structures.md)
