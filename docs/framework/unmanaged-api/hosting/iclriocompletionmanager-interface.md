---
title: Интерфейс ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: e23675351e1fd0de510243c9ee8b3a6dd6f29cec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714124"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="fc180-102">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fc180-102">ICLRIoCompletionManager Interface</span></span>

<span data-ttu-id="fc180-103">Реализует метод обратного вызова, который позволяет узлу уведомлять среду CLR о состоянии указанных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="fc180-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc180-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fc180-104">Methods</span></span>  
  
|<span data-ttu-id="fc180-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fc180-105">Method</span></span>|<span data-ttu-id="fc180-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fc180-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc180-107">Метод OnComplete</span><span class="sxs-lookup"><span data-stu-id="fc180-107">OnComplete Method</span></span>](iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="fc180-108">Сообщает среде CLR о состоянии запроса ввода-вывода, сделанного с помощью вызова метода [IHostIoCompletionManager:: BIND](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fc180-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc180-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fc180-109">Remarks</span></span>  

 <span data-ttu-id="fc180-110">Узел реализует абстракцию завершения ввода-вывода с помощью интерфейса [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fc180-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="fc180-111">CLR выполняет запросы ввода-вывода через этот интерфейс, и узел уведомляет среду выполнения о результатах таких запросов с помощью `ICLRIoCompletionManager` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="fc180-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc180-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fc180-112">Requirements</span></span>  

 <span data-ttu-id="fc180-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc180-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc180-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc180-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc180-115">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc180-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc180-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc180-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc180-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fc180-117">See also</span></span>

- [<span data-ttu-id="fc180-118">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fc180-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="fc180-119">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="fc180-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="fc180-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="fc180-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
