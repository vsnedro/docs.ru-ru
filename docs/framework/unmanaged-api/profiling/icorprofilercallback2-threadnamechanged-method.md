---
title: Метод ICorProfilerCallback2::ThreadNameChanged
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
ms.openlocfilehash: 8398febd17c7e77f2ad281ebeafc138fca4a47d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718037"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="5f92f-102">Метод ICorProfilerCallback2::ThreadNameChanged</span><span class="sxs-lookup"><span data-stu-id="5f92f-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>

<span data-ttu-id="5f92f-103">Уведомляет профилировщик кода о том, что имя потока изменилось.</span><span class="sxs-lookup"><span data-stu-id="5f92f-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f92f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f92f-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f92f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f92f-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="5f92f-106">окне Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="5f92f-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5f92f-107">окне Длина нового имени потока.</span><span class="sxs-lookup"><span data-stu-id="5f92f-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="5f92f-108">окне Новое имя потока.</span><span class="sxs-lookup"><span data-stu-id="5f92f-108">[in] The new name of the thread.</span></span> <span data-ttu-id="5f92f-109">Имя не завершается нулем.</span><span class="sxs-lookup"><span data-stu-id="5f92f-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f92f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5f92f-110">Requirements</span></span>  

 <span data-ttu-id="5f92f-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f92f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f92f-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f92f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f92f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f92f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f92f-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f92f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f92f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5f92f-115">See also</span></span>

- [<span data-ttu-id="5f92f-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5f92f-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5f92f-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="5f92f-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
