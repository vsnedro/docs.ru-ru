---
title: Метод IHostTask::Start
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: 4143c3d25dd5262a10b53708a249910cc79f5314
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720442"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="d568e-102">Метод IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="d568e-102">IHostTask::Start Method</span></span>

<span data-ttu-id="d568e-103">Запрашивает, что узел перемещает задачу, представленную текущим экземпляром [IHostTask](ihosttask-interface.md) , из приостановленного в активное состояние, в котором можно выполнить код.</span><span class="sxs-lookup"><span data-stu-id="d568e-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d568e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d568e-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d568e-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d568e-105">Return Value</span></span>  
  
|<span data-ttu-id="d568e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d568e-106">HRESULT</span></span>|<span data-ttu-id="d568e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d568e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d568e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d568e-108">S_OK</span></span>|<span data-ttu-id="d568e-109">Успешное начало возврата.</span><span class="sxs-lookup"><span data-stu-id="d568e-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="d568e-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d568e-110">E_FAIL</span></span>|<span data-ttu-id="d568e-111">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d568e-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d568e-112">Когда метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d568e-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="d568e-113">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d568e-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d568e-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d568e-114">Remarks</span></span>  

 <span data-ttu-id="d568e-115">`Start` всегда возвращает значение HRESULT, равное S_OK, за исключением случаев, когда произошла разрушительная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d568e-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d568e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d568e-116">Requirements</span></span>  

 <span data-ttu-id="d568e-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d568e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d568e-118">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d568e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d568e-119">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d568e-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d568e-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d568e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d568e-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d568e-121">See also</span></span>

- [<span data-ttu-id="d568e-122">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d568e-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="d568e-123">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d568e-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="d568e-124">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="d568e-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="d568e-125">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d568e-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
