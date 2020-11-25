---
title: Метод ICLRTaskManager::SetUILocale
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
ms.openlocfilehash: a426fca1b7ca4bfb9cbb30a221859f7c114db682
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732433"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="659b5-102">Метод ICLRTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="659b5-102">ICLRTaskManager::SetUILocale Method</span></span>

<span data-ttu-id="659b5-103">Уведомляет среду CLR о том, что узел изменил языковой стандарт пользовательского интерфейса (UI) или язык и региональные параметры, в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="659b5-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="659b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="659b5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="659b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="659b5-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="659b5-106">окне Значение идентификатора локали, сопоставленное с вновь назначенным географическим языком и региональными параметрами пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="659b5-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="659b5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="659b5-107">Return Value</span></span>  
  
|<span data-ttu-id="659b5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="659b5-108">HRESULT</span></span>|<span data-ttu-id="659b5-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="659b5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="659b5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="659b5-110">S_OK</span></span>|<span data-ttu-id="659b5-111">`SetUILocale` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="659b5-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="659b5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="659b5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="659b5-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="659b5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="659b5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="659b5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="659b5-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="659b5-115">The call timed out.</span></span>|  
|<span data-ttu-id="659b5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="659b5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="659b5-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="659b5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="659b5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="659b5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="659b5-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="659b5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="659b5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="659b5-120">E_FAIL</span></span>|<span data-ttu-id="659b5-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="659b5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="659b5-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="659b5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="659b5-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="659b5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="659b5-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="659b5-124">Remarks</span></span>  

 <span data-ttu-id="659b5-125">`SetUILocale` Предоставляет узлу возможность выполнять любые механизмы, необходимые для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="659b5-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="659b5-126">Требования</span><span class="sxs-lookup"><span data-stu-id="659b5-126">Requirements</span></span>  

 <span data-ttu-id="659b5-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="659b5-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="659b5-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="659b5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="659b5-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="659b5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="659b5-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="659b5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659b5-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="659b5-131">See also</span></span>

- [<span data-ttu-id="659b5-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="659b5-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="659b5-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="659b5-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="659b5-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="659b5-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="659b5-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="659b5-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
