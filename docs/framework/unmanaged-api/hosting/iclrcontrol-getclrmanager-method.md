---
title: Метод ICLRControl::GetCLRManager
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: d18b3a5c06ac0d3a86f7823f3b140c76c6c9a746
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728359"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="d30b0-102">Метод ICLRControl::GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="d30b0-102">ICLRControl::GetCLRManager Method</span></span>

<span data-ttu-id="d30b0-103">Возвращает указатель интерфейса на экземпляр любого из типов диспетчера, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d30b0-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d30b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d30b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d30b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d30b0-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="d30b0-106">окне `IID` Тип возвращаемого типа диспетчера.</span><span class="sxs-lookup"><span data-stu-id="d30b0-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="d30b0-107">`IID`Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d30b0-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="d30b0-108">IID_ICLRDebugManager: указывает, что `ppObject` будет иметь тип [ICLRDebugManager](iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="d30b0-109">IID_ICLRErrorReportingManager: указывает, что `ppObject` будет иметь тип [iclrerrorreportingmanagergetbucketparametersforcurrentexception](iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="d30b0-110">IID_ICLRGCManager: указывает, что `ppObject` будет иметь тип [иклргкманажер](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="d30b0-111">IID_ICLRHostProtectionManager: указывает, что `ppObject` будет иметь тип [иклрхостпротектионманажер](iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="d30b0-112">IID_ICLROnEventManager: указывает, что `ppObject` будет иметь тип [ICLROnEventManager](iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="d30b0-113">IID_ICLRPolicyManager: указывает, что `ppObject` будет иметь тип [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="d30b0-114">IID_ICLRTaskManager: указывает, что `ppObject` будет иметь тип [ICLRTaskManager](iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="d30b0-115">заполняет Указатель интерфейса на запрошенный диспетчер или значение null, если был запрошен недопустимый тип диспетчера.</span><span class="sxs-lookup"><span data-stu-id="d30b0-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d30b0-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d30b0-116">Return Value</span></span>  
  
|<span data-ttu-id="d30b0-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d30b0-117">HRESULT</span></span>|<span data-ttu-id="d30b0-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="d30b0-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d30b0-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d30b0-119">S_OK</span></span>|<span data-ttu-id="d30b0-120">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="d30b0-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="d30b0-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d30b0-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d30b0-122">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d30b0-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d30b0-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d30b0-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d30b0-124">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d30b0-124">The call timed out.</span></span>|  
|<span data-ttu-id="d30b0-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d30b0-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d30b0-126">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d30b0-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d30b0-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d30b0-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d30b0-128">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d30b0-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d30b0-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d30b0-129">E_FAIL</span></span>|<span data-ttu-id="d30b0-130">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d30b0-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d30b0-131">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d30b0-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d30b0-132">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d30b0-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d30b0-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="d30b0-133">E_NOINTERFACE</span></span>|<span data-ttu-id="d30b0-134">Тип интерфейса не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d30b0-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d30b0-135">Требования</span><span class="sxs-lookup"><span data-stu-id="d30b0-135">Requirements</span></span>  

 <span data-ttu-id="d30b0-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d30b0-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d30b0-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d30b0-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d30b0-138">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d30b0-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d30b0-139">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d30b0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30b0-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d30b0-140">See also</span></span>

- [<span data-ttu-id="d30b0-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="d30b0-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d30b0-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="d30b0-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
