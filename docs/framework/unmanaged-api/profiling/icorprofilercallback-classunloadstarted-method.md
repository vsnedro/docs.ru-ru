---
title: Метод ICorProfilerCallback::ClassUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 1c154eee85811796321aea2647db1c8996997576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700253"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="b3371-102">Метод ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="b3371-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>

<span data-ttu-id="b3371-103">Уведомляет профилировщик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="b3371-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3371-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3371-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3371-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3371-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="b3371-106">\[в] определяет класс, который выгружается.</span><span class="sxs-lookup"><span data-stu-id="b3371-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3371-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b3371-107">Remarks</span></span>  

 <span data-ttu-id="b3371-108">Значение недопустимо `classId` для информационного запроса после `ClassUnloadStarted` возврата метода — это последний шанс профилировщика получить сведения об этом классе.</span><span class="sxs-lookup"><span data-stu-id="b3371-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3371-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b3371-109">Requirements</span></span>  

 <span data-ttu-id="b3371-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3371-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3371-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3371-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3371-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3371-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3371-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3371-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3371-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3371-114">See also</span></span>

- [<span data-ttu-id="b3371-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b3371-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b3371-116">Метод ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="b3371-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
