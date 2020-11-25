---
title: Метод ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 32483be43d4d4fe9d185c091e15a13c6feb95600
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728827"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="b9317-102">Метод ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="b9317-102">ICLRRuntimeHost::SetHostControl Method</span></span>

<span data-ttu-id="b9317-103">Задает указатель интерфейса, который среда CLR может использовать для получения реализации [интерфейса IHostControl](ihostcontrol-interface.md)в узле.</span><span class="sxs-lookup"><span data-stu-id="b9317-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9317-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9317-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9317-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9317-105">Parameters</span></span>  

 `pHostControl`  
 <span data-ttu-id="b9317-106">окне Указатель интерфейса на реализацию [интерфейса IHostControl](ihostcontrol-interface.md)узла.</span><span class="sxs-lookup"><span data-stu-id="b9317-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9317-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9317-107">Return Value</span></span>  
  
|<span data-ttu-id="b9317-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9317-108">HRESULT</span></span>|<span data-ttu-id="b9317-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="b9317-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9317-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9317-110">S_OK</span></span>|<span data-ttu-id="b9317-111">`SetHostControl` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b9317-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="b9317-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9317-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9317-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b9317-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9317-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9317-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9317-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b9317-115">The call timed out.</span></span>|  
|<span data-ttu-id="b9317-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9317-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9317-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b9317-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9317-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9317-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9317-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b9317-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9317-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9317-120">E_FAIL</span></span>|<span data-ttu-id="b9317-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b9317-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9317-122">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b9317-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9317-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b9317-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b9317-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="b9317-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="b9317-125">Среда CLR уже инициализирована.</span><span class="sxs-lookup"><span data-stu-id="b9317-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9317-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b9317-126">Remarks</span></span>  

 <span data-ttu-id="b9317-127">Необходимо вызвать `SetHostControl` перед инициализацией среды CLR, то есть до вызова [метода Start](iclrruntimehost-start-method.md) или использования любого [интерфейса метаданных](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="b9317-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="b9317-128">Рекомендуется вызывать `SetHostControl` немедленно после вызова [функции Корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md) или [функции CorBindToRuntimeEx](corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="b9317-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9317-129">Требования</span><span class="sxs-lookup"><span data-stu-id="b9317-129">Requirements</span></span>  

 <span data-ttu-id="b9317-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9317-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9317-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b9317-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9317-132">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9317-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9317-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9317-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9317-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b9317-134">See also</span></span>

- [<span data-ttu-id="b9317-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b9317-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="b9317-136">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="b9317-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
