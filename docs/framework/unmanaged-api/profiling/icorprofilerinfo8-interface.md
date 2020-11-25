---
title: Интерфейс ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: eedd16006781de517587e5138543b9b9eca3ff90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733611"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="8a353-102">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="8a353-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="8a353-103">Подкласс [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , предоставляющий методы для запроса сведений о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="8a353-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="8a353-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8a353-104">Methods</span></span>  

| <span data-ttu-id="8a353-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8a353-105">Method</span></span>|<span data-ttu-id="8a353-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8a353-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="8a353-107">Метод IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="8a353-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="8a353-108">Определяет, имеет ли функция связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="8a353-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="8a353-109">Метод GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="8a353-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="8a353-110">Сопоставляет указатель инструкции управляемого кода с FunctionID.</span><span class="sxs-lookup"><span data-stu-id="8a353-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="8a353-111">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="8a353-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="8a353-112">Метод GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="8a353-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="8a353-113">Извлекает сведения о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="8a353-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="8a353-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8a353-114">Requirements</span></span>  

<span data-ttu-id="8a353-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a353-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8a353-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a353-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="8a353-117">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8a353-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8a353-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8a353-118">See also</span></span>

- [<span data-ttu-id="8a353-119">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8a353-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
