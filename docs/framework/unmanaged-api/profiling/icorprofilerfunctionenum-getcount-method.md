---
title: Метод ICorProfilerFunctionEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
ms.openlocfilehash: 3ccf75523eb9362b8ef5c38d224a419502cb8b92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724150"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="f646a-102">Метод ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="f646a-102">ICorProfilerFunctionEnum::GetCount Method</span></span>

<span data-ttu-id="f646a-103">Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="f646a-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f646a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f646a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f646a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f646a-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f646a-106">заполняет Число загруженных функций.</span><span class="sxs-lookup"><span data-stu-id="f646a-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f646a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f646a-107">Requirements</span></span>  

 <span data-ttu-id="f646a-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f646a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f646a-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f646a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f646a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f646a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f646a-111">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f646a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f646a-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f646a-112">See also</span></span>

- [<span data-ttu-id="f646a-113">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="f646a-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="f646a-114">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f646a-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
