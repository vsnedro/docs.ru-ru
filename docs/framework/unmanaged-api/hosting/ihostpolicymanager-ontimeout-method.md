---
title: Метод IHostPolicyManager::OnTimeout
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: e3f2dc7ff9beaf417184f3d09db76e611982118a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690672"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="284f7-102">Метод IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="284f7-102">IHostPolicyManager::OnTimeout Method</span></span>

<span data-ttu-id="284f7-103">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононтимеаут](iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="284f7-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="284f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="284f7-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="284f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="284f7-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="284f7-106">окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее тип операции, для которой истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="284f7-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="284f7-107">окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие, ВЫПОЛНЯЕМое средой CLR в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="284f7-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="284f7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="284f7-108">Return Value</span></span>  
  
|<span data-ttu-id="284f7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="284f7-109">HRESULT</span></span>|<span data-ttu-id="284f7-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="284f7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="284f7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="284f7-111">S_OK</span></span>|<span data-ttu-id="284f7-112">`OnTimeout` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="284f7-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="284f7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="284f7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="284f7-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="284f7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="284f7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="284f7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="284f7-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="284f7-116">The call timed out.</span></span>|  
|<span data-ttu-id="284f7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="284f7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="284f7-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="284f7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="284f7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="284f7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="284f7-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="284f7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="284f7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="284f7-121">E_FAIL</span></span>|<span data-ttu-id="284f7-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="284f7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="284f7-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="284f7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="284f7-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="284f7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="284f7-125">Требования</span><span class="sxs-lookup"><span data-stu-id="284f7-125">Requirements</span></span>  

 <span data-ttu-id="284f7-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="284f7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="284f7-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="284f7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="284f7-128">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="284f7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="284f7-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="284f7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="284f7-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="284f7-130">See also</span></span>

- [<span data-ttu-id="284f7-131">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="284f7-131">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="284f7-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="284f7-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="284f7-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="284f7-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="284f7-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="284f7-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
