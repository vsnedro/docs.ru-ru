---
title: Интерфейс IHostPolicyManager
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: db089a55128fa675ceedf157b046fe205d8c6b51
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804330"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="3f83b-102">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3f83b-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="3f83b-103">Предоставляет методы, уведомляющие узел о действиях, выполняемых средой CLR в случае прерываний, времени ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="3f83b-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f83b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3f83b-104">Methods</span></span>  
  
|<span data-ttu-id="3f83b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3f83b-105">Method</span></span>|<span data-ttu-id="3f83b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3f83b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f83b-107">Метод OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="3f83b-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="3f83b-108">Уведомляет основное приложение о том, что среда CLR собирается принять действие по умолчанию, заданное вызовом метода [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) в ответ на прерывание или <xref:System.AppDomain> выгрузку потока.</span><span class="sxs-lookup"><span data-stu-id="3f83b-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="3f83b-109">Метод OnFailure</span><span class="sxs-lookup"><span data-stu-id="3f83b-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="3f83b-110">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом [ICLRPolicyManager:: сетактиононфаилуре](iclrpolicymanager-setactiononfailure-method.md) в ответ на выделение ресурсов или сбой при реорганизации.</span><span class="sxs-lookup"><span data-stu-id="3f83b-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="3f83b-111">Метод OnTimeout</span><span class="sxs-lookup"><span data-stu-id="3f83b-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="3f83b-112">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононтимеаут](iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="3f83b-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f83b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3f83b-113">Requirements</span></span>  
 <span data-ttu-id="3f83b-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f83b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f83b-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3f83b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f83b-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3f83b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f83b-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f83b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f83b-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3f83b-118">See also</span></span>

- [<span data-ttu-id="3f83b-119">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="3f83b-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="3f83b-120">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="3f83b-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="3f83b-121">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="3f83b-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="3f83b-122">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3f83b-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="3f83b-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3f83b-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
