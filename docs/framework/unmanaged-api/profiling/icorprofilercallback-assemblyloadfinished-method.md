---
title: Метод ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: ce4a842bc71ff144e46efb0d6f7068dfca9d207d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500446"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="2e0c2-102">Метод ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="2e0c2-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="2e0c2-103">Уведомляет профилировщик о том, что загрузка сборки завершена.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e0c2-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e0c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e0c2-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="2e0c2-106">\[в] определяет сборку, которая была загружена.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="2e0c2-107">\[in] значение HRESULT, указывающее, успешно ли завершена загрузка сборки.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e0c2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e0c2-108">Remarks</span></span>  
 <span data-ttu-id="2e0c2-109">Значение недопустимо `assemblyId` для информационного запроса до `AssemblyLoadFinished` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="2e0c2-110">Некоторые части загрузки сборки могут продолжаться после `AssemblyLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="2e0c2-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2e0c2-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть загрузки сборки завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="2e0c2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e0c2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2e0c2-113">Requirements</span></span>  
 <span data-ttu-id="2e0c2-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e0c2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e0c2-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e0c2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e0c2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e0c2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e0c2-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e0c2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0c2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2e0c2-118">See also</span></span>

- [<span data-ttu-id="2e0c2-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2e0c2-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
