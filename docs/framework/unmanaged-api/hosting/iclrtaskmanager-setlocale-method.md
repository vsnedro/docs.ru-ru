---
title: Метод ICLRTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
ms.openlocfilehash: 5f799c140705a5279c996b6bec90ab1f29bd42ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732441"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="88b57-102">Метод ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="88b57-102">ICLRTaskManager::SetLocale Method</span></span>

<span data-ttu-id="88b57-103">Уведомляет среду CLR о том, что узел изменил значение идентификатора локали (который сопоставляется с географическим языком и региональными параметрами) в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="88b57-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88b57-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88b57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88b57-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="88b57-106">окне Значение идентификатора локали, сопоставляемое с новым назначенным географическим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="88b57-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88b57-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88b57-107">Return Value</span></span>  
  
|<span data-ttu-id="88b57-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88b57-108">HRESULT</span></span>|<span data-ttu-id="88b57-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="88b57-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88b57-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="88b57-110">S_OK</span></span>|<span data-ttu-id="88b57-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="88b57-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="88b57-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="88b57-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88b57-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="88b57-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88b57-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88b57-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88b57-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="88b57-115">The call timed out.</span></span>|  
|<span data-ttu-id="88b57-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88b57-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88b57-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="88b57-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88b57-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88b57-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88b57-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="88b57-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88b57-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88b57-120">E_FAIL</span></span>|<span data-ttu-id="88b57-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="88b57-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88b57-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="88b57-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88b57-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="88b57-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88b57-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="88b57-124">Remarks</span></span>  

 <span data-ttu-id="88b57-125">`SetLocale` Предоставляет узлу возможность выполнения любых механизмов, которые могут потребоваться для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="88b57-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88b57-126">Требования</span><span class="sxs-lookup"><span data-stu-id="88b57-126">Requirements</span></span>  

 <span data-ttu-id="88b57-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88b57-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88b57-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="88b57-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88b57-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88b57-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88b57-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88b57-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b57-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="88b57-131">See also</span></span>

- [<span data-ttu-id="88b57-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="88b57-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="88b57-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="88b57-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="88b57-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="88b57-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="88b57-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="88b57-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
