---
title: Метод IHostTask::GetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: e41fcf2f03b024c1b4ae0032c0ff025d6e2aa1c3
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842508"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="f994e-102">Метод IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="f994e-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="f994e-103">Возвращает уровень приоритета потока задачи, представленной текущим экземпляром [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f994e-103">Gets the thread priority level of the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f994e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f994e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f994e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f994e-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="f994e-106">заполняет Указатель на целое число, указывающий уровень приоритета потока задачи, представленной текущим `IHostTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="f994e-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f994e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f994e-107">Return Value</span></span>  
  
|<span data-ttu-id="f994e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f994e-108">HRESULT</span></span>|<span data-ttu-id="f994e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f994e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f994e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f994e-110">S_OK</span></span>|<span data-ttu-id="f994e-111">`GetPriority`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f994e-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="f994e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f994e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f994e-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f994e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f994e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f994e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f994e-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f994e-115">The call timed out.</span></span>|  
|<span data-ttu-id="f994e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f994e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f994e-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f994e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f994e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f994e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f994e-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f994e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f994e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f994e-120">E_FAIL</span></span>|<span data-ttu-id="f994e-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f994e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f994e-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f994e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f994e-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f994e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f994e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="f994e-124">Remarks</span></span>  
 <span data-ttu-id="f994e-125">Значения уровня приоритета потока определяются функцией Win32 `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="f994e-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f994e-126">Требования</span><span class="sxs-lookup"><span data-stu-id="f994e-126">Requirements</span></span>  
 <span data-ttu-id="f994e-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f994e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f994e-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f994e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f994e-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f994e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f994e-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f994e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f994e-131">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f994e-131">See also</span></span>

- [<span data-ttu-id="f994e-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f994e-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f994e-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f994e-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f994e-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f994e-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f994e-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f994e-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
