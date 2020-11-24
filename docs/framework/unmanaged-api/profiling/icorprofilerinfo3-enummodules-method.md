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
ms.openlocfilehash: 698f6abc872a7e072ae47520386aa9c7ddfb44fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681474"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="6d045-102">Метод ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="6d045-102">ICorProfilerInfo3::EnumModules Method</span></span>

<span data-ttu-id="6d045-103">Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="6d045-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d045-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d045-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d045-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d045-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="6d045-106">заполняет Указатель на интерфейс [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6d045-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d045-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d045-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d045-108">Требования</span><span class="sxs-lookup"><span data-stu-id="6d045-108">Requirements</span></span>  

 <span data-ttu-id="6d045-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d045-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d045-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d045-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d045-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d045-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d045-112">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d045-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d045-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6d045-113">See also</span></span>

- [<span data-ttu-id="6d045-114">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="6d045-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="6d045-115">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="6d045-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="6d045-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6d045-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6d045-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="6d045-117">Profiling</span></span>](index.md)
