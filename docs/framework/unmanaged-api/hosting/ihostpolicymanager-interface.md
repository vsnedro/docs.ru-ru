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
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503943"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="31a94-102">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="31a94-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="31a94-103">Предоставляет методы, уведомляющие узел о действиях, выполняемых средой CLR в случае прерываний, времени ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="31a94-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31a94-104">Методы</span><span class="sxs-lookup"><span data-stu-id="31a94-104">Methods</span></span>  
  
|<span data-ttu-id="31a94-105">Метод</span><span class="sxs-lookup"><span data-stu-id="31a94-105">Method</span></span>|<span data-ttu-id="31a94-106">Описание</span><span class="sxs-lookup"><span data-stu-id="31a94-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31a94-107">Метод OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="31a94-107">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="31a94-108">Уведомляет основное приложение о том, что среда CLR собирается принять действие по умолчанию, заданное вызовом метода [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) в ответ на прерывание или <xref:System.AppDomain> выгрузку потока.</span><span class="sxs-lookup"><span data-stu-id="31a94-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="31a94-109">Метод OnFailure</span><span class="sxs-lookup"><span data-stu-id="31a94-109">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="31a94-110">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом [ICLRPolicyManager:: сетактиононфаилуре](iclrpolicymanager-setactiononfailure-method.md) в ответ на выделение ресурсов или сбой при реорганизации.</span><span class="sxs-lookup"><span data-stu-id="31a94-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="31a94-111">Метод OnTimeout</span><span class="sxs-lookup"><span data-stu-id="31a94-111">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="31a94-112">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононтимеаут](iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="31a94-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31a94-113">Требования</span><span class="sxs-lookup"><span data-stu-id="31a94-113">Requirements</span></span>  
 <span data-ttu-id="31a94-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31a94-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31a94-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="31a94-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31a94-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="31a94-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31a94-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31a94-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a94-118">См. также</span><span class="sxs-lookup"><span data-stu-id="31a94-118">See also</span></span>

- [<span data-ttu-id="31a94-119">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="31a94-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="31a94-120">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="31a94-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="31a94-121">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="31a94-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="31a94-122">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="31a94-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="31a94-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="31a94-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
