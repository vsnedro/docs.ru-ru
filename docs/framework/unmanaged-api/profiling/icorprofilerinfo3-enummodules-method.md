---
title: Метод ICorProfilerInfo3::EnumModules
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
ms.openlocfilehash: 85adf2dbdbb8c02192a9017bc4f664274a08ee24
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496585"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="0ffd6-102">Метод ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="0ffd6-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="0ffd6-103">Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="0ffd6-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ffd6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ffd6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ffd6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ffd6-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="0ffd6-106">заполняет Указатель на интерфейс [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0ffd6-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ffd6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ffd6-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ffd6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0ffd6-108">Requirements</span></span>  
 <span data-ttu-id="0ffd6-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ffd6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ffd6-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ffd6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ffd6-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ffd6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ffd6-112">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ffd6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffd6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0ffd6-113">See also</span></span>

- [<span data-ttu-id="0ffd6-114">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="0ffd6-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="0ffd6-115">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="0ffd6-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="0ffd6-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="0ffd6-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0ffd6-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="0ffd6-117">Profiling</span></span>](index.md)
