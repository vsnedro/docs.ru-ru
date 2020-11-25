---
title: Метод ICLRDebugManager::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: 71e11d7db3bd679e7972fb2f6ce098edc3399885
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731024"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="f97d3-102">Метод ICLRDebugManager::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="f97d3-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>

<span data-ttu-id="f97d3-103">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="f97d3-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f97d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f97d3-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f97d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f97d3-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="f97d3-106">[out] `true` значение, если отладчик присоединен к процессу; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="f97d3-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f97d3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f97d3-107">Return Value</span></span>  
  
|<span data-ttu-id="f97d3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f97d3-108">HRESULT</span></span>|<span data-ttu-id="f97d3-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="f97d3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f97d3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f97d3-110">S_OK</span></span>|<span data-ttu-id="f97d3-111">`IsDebuggerAttached` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f97d3-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="f97d3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f97d3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f97d3-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f97d3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f97d3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f97d3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f97d3-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f97d3-115">The call timed out.</span></span>|  
|<span data-ttu-id="f97d3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f97d3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f97d3-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f97d3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f97d3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f97d3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f97d3-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f97d3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f97d3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f97d3-120">E_FAIL</span></span>|<span data-ttu-id="f97d3-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f97d3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f97d3-122">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f97d3-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f97d3-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f97d3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f97d3-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f97d3-124">Remarks</span></span>  

 <span data-ttu-id="f97d3-125">`IsDebuggerAttached` позволяет основному приложению запрашивать среду CLR, чтобы определить, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="f97d3-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f97d3-126">Требования</span><span class="sxs-lookup"><span data-stu-id="f97d3-126">Requirements</span></span>  

 <span data-ttu-id="f97d3-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f97d3-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f97d3-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f97d3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f97d3-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f97d3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f97d3-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f97d3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f97d3-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f97d3-131">See also</span></span>

- [<span data-ttu-id="f97d3-132">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f97d3-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f97d3-133">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="f97d3-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="f97d3-134">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="f97d3-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)
