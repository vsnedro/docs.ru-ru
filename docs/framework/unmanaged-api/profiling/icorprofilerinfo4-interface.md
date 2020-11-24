---
title: Интерфейс ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c3e623b0b5f8b49e043fe3a1aa8311558e573573
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682839"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="2c9bf-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="2c9bf-102">ICorProfilerInfo4 Interface</span></span>

<span data-ttu-id="2c9bf-103">Предоставляет методы, используемые профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий и сведениями о запросах.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="2c9bf-104">.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-104">.</span></span> <span data-ttu-id="2c9bf-105">`ICorProfilerInfo4`Интерфейс является расширением других `ICorProfilerInfo` интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="2c9bf-106">Он предоставляет новые методы для поддержки повторной компиляции JIT, добавленной в .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c9bf-107">Методы</span><span class="sxs-lookup"><span data-stu-id="2c9bf-107">Methods</span></span>  
  
|<span data-ttu-id="2c9bf-108">Метод</span><span class="sxs-lookup"><span data-stu-id="2c9bf-108">Method</span></span>|<span data-ttu-id="2c9bf-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2c9bf-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c9bf-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="2c9bf-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="2c9bf-111">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="2c9bf-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="2c9bf-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="2c9bf-113">Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="2c9bf-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="2c9bf-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="2c9bf-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="2c9bf-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="2c9bf-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="2c9bf-117">Сопоставляет указатель инструкции управляемого кода с JIT-повторно скомпилированной версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="2c9bf-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="2c9bf-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="2c9bf-119">Возвращает карту из смещений MSIL к собственным смещениям для кода, содержащегося в JIT-повторно скомпилированной версии указанной функции.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="2c9bf-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="2c9bf-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="2c9bf-121">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="2c9bf-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="2c9bf-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="2c9bf-123">Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="2c9bf-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="2c9bf-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="2c9bf-125">Инициализирует текущий поток перед последовательными вызовами API профилировщика в том же потоке, что позволяет избежать взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="2c9bf-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="2c9bf-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="2c9bf-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="2c9bf-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="2c9bf-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="2c9bf-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c9bf-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2c9bf-130">Remarks</span></span>  

 <span data-ttu-id="2c9bf-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="2c9bf-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="2c9bf-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="2c9bf-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c9bf-134">Требования</span><span class="sxs-lookup"><span data-stu-id="2c9bf-134">Requirements</span></span>  

 <span data-ttu-id="2c9bf-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c9bf-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c9bf-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c9bf-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c9bf-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c9bf-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c9bf-138">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c9bf-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9bf-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c9bf-139">See also</span></span>

- [<span data-ttu-id="2c9bf-140">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="2c9bf-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2c9bf-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2c9bf-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
