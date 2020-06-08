---
title: Метод ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: ccbb051ac30fb25199ce12c16fff74bb0b9944fa
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495090"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="a13a7-102">Метод ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="a13a7-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="a13a7-103">Получает указатель интерфейса на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a13a7-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a13a7-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a13a7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a13a7-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a13a7-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="a13a7-107">Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a13a7-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="a13a7-108">Однако начальная позиции курсора копии совпадает с текущей позицией курсора этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a13a7-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13a7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a13a7-109">Requirements</span></span>  
 <span data-ttu-id="a13a7-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a13a7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13a7-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a13a7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a13a7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a13a7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a13a7-113">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13a7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a13a7-114">See also</span></span>

- [<span data-ttu-id="a13a7-115">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="a13a7-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="a13a7-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a13a7-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
