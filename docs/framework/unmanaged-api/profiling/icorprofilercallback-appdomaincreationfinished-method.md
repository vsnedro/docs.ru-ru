---
title: Метод ICorProfilerCallback::AppDomainCreationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 688b9975cc68463de066e5225c6ab1e04cbb5337
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685385"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="7162c-102">Метод ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="7162c-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>

<span data-ttu-id="7162c-103">Уведомляет профилировщик о том, что домен приложения создан.</span><span class="sxs-lookup"><span data-stu-id="7162c-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7162c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7162c-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="7162c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7162c-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="7162c-106">\[в] определяет домен, который был создан.</span><span class="sxs-lookup"><span data-stu-id="7162c-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="7162c-107">\[в] значение HRESULT, указывающее, успешно ли создана область приложения.</span><span class="sxs-lookup"><span data-stu-id="7162c-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="7162c-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7162c-108">Remarks</span></span>  

 <span data-ttu-id="7162c-109">Идентификатор приложения не является допустимым для запроса информации до `AppDomainCreationFinished` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="7162c-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="7162c-110">Некоторые части загрузки домена приложения могут продолжаться после `AppDomainCreationFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7162c-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="7162c-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="7162c-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="7162c-112">Однако значение HRESULT в случае успеха в `hrStatus` указывает, что первая часть создания домена приложения успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="7162c-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7162c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7162c-113">Requirements</span></span>  

 <span data-ttu-id="7162c-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7162c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7162c-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7162c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7162c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7162c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7162c-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7162c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7162c-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7162c-118">See also</span></span>

- [<span data-ttu-id="7162c-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7162c-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
