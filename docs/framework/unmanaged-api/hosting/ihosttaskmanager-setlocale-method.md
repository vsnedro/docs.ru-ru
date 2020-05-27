---
title: Метод IHostTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: 841827017262b731fd5e6f6bd0b5862fecaf2744
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841728"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="6792a-102">Метод IHostTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="6792a-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="6792a-103">Уведомляет основное приложение о том, что среда CLR изменила языковой стандарт, или культуру, в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="6792a-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6792a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6792a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6792a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6792a-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="6792a-106">окне Значение идентификатора локали, сопоставляемое с новым назначенным географическим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="6792a-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6792a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6792a-107">Return Value</span></span>  
  
|<span data-ttu-id="6792a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6792a-108">HRESULT</span></span>|<span data-ttu-id="6792a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6792a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6792a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6792a-110">S_OK</span></span>|<span data-ttu-id="6792a-111">`SetLocale`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6792a-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="6792a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6792a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6792a-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6792a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6792a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6792a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6792a-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="6792a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6792a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6792a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6792a-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="6792a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6792a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6792a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6792a-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="6792a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6792a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6792a-120">E_FAIL</span></span>|<span data-ttu-id="6792a-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6792a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6792a-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6792a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6792a-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6792a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6792a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="6792a-124">E_NOTIMPL</span></span>|<span data-ttu-id="6792a-125">Узел не позволяет управляемому пользовательскому коду изменять языковой стандарт.</span><span class="sxs-lookup"><span data-stu-id="6792a-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6792a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="6792a-126">Remarks</span></span>  
 <span data-ttu-id="6792a-127">Среда выполнения вызывает `SetLocale` , когда значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> свойства изменяется управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="6792a-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="6792a-128">Этот метод предоставляет узлу возможность выполнять любые механизмы, которые могут потребоваться для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="6792a-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="6792a-129">Если узел не позволяет изменить языковой стандарт из управляемого кода или не реализует механизм для синхронизации языковых стандартов, он должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="6792a-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6792a-130">Требования</span><span class="sxs-lookup"><span data-stu-id="6792a-130">Requirements</span></span>  
 <span data-ttu-id="6792a-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6792a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6792a-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6792a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6792a-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6792a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6792a-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6792a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6792a-135">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="6792a-135">See also</span></span>

- [<span data-ttu-id="6792a-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6792a-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6792a-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6792a-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6792a-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="6792a-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6792a-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6792a-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6792a-140">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="6792a-140">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)
