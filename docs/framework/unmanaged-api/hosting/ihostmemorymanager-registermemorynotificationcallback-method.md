---
title: Метод IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 0c20df85560f715e829fe02be599788854fcb0f1
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804478"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="9aa65-102">Метод IHostMemoryManager::RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="9aa65-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="9aa65-103">Регистрирует указатель на функцию обратного вызова, которую вызывает хост для уведомления среды CLR о текущей загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9aa65-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9aa65-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aa65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9aa65-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="9aa65-106">окне Указатель интерфейса на экземпляр [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) , РЕАЛИЗОВАНный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9aa65-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aa65-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9aa65-107">Return Value</span></span>  
  
|<span data-ttu-id="9aa65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9aa65-108">HRESULT</span></span>|<span data-ttu-id="9aa65-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9aa65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9aa65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9aa65-110">S_OK</span></span>|<span data-ttu-id="9aa65-111">`RegisterMemoryNotificationCallback`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="9aa65-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="9aa65-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9aa65-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9aa65-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9aa65-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9aa65-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9aa65-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9aa65-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="9aa65-115">The call timed out.</span></span>|  
|<span data-ttu-id="9aa65-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9aa65-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9aa65-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="9aa65-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9aa65-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9aa65-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9aa65-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="9aa65-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9aa65-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9aa65-120">E_FAIL</span></span>|<span data-ttu-id="9aa65-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9aa65-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9aa65-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9aa65-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9aa65-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9aa65-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aa65-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="9aa65-124">Remarks</span></span>  
 <span data-ttu-id="9aa65-125">Поскольку `ICLRMemoryNotificationCallback` интерфейс определяет только один метод ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) и `pCallback` является указателем на `ICLRMemoryNotificationCallback` экземпляр, предоставляемый средой CLR, регистрация фактически осуществляется для самой функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="9aa65-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="9aa65-126">Узел вызывает `OnMemoryNotification` функцию, чтобы сообщить об условиях нехватки памяти, вместо использования стандартной `CreateMemoryResourceNotification` функции Win32.</span><span class="sxs-lookup"><span data-stu-id="9aa65-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="9aa65-127">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="9aa65-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9aa65-128">Вызовы `OnMemoryNotification` никогда не блокируются.</span><span class="sxs-lookup"><span data-stu-id="9aa65-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="9aa65-129">Они всегда возвращают немедленно.</span><span class="sxs-lookup"><span data-stu-id="9aa65-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aa65-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9aa65-130">Requirements</span></span>  
 <span data-ttu-id="9aa65-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aa65-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aa65-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9aa65-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9aa65-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9aa65-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9aa65-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aa65-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa65-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9aa65-135">See also</span></span>

- [<span data-ttu-id="9aa65-136">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="9aa65-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="9aa65-137">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="9aa65-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
