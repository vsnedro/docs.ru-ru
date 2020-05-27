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
ms.openlocfilehash: a4e8211f091b2a3a4f24d8350f6d7dbe7d7920af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842391"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="7aebc-102">Метод IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="7aebc-102">IHostTask::Start Method</span></span>
<span data-ttu-id="7aebc-103">Запрашивает, что узел перемещает задачу, представленную текущим экземпляром [IHostTask](ihosttask-interface.md) , из приостановленного в активное состояние, в котором можно выполнить код.</span><span class="sxs-lookup"><span data-stu-id="7aebc-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aebc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7aebc-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7aebc-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7aebc-105">Return Value</span></span>  
  
|<span data-ttu-id="7aebc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7aebc-106">HRESULT</span></span>|<span data-ttu-id="7aebc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7aebc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7aebc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7aebc-108">S_OK</span></span>|<span data-ttu-id="7aebc-109">Успешное начало возврата.</span><span class="sxs-lookup"><span data-stu-id="7aebc-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="7aebc-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7aebc-110">E_FAIL</span></span>|<span data-ttu-id="7aebc-111">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7aebc-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7aebc-112">Когда метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7aebc-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="7aebc-113">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7aebc-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aebc-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="7aebc-114">Remarks</span></span>  
 <span data-ttu-id="7aebc-115">`Start`всегда возвращает значение HRESULT, равное S_OK, за исключением случаев, когда произошла разрушительная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7aebc-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aebc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7aebc-116">Requirements</span></span>  
 <span data-ttu-id="7aebc-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aebc-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aebc-118">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7aebc-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7aebc-119">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7aebc-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7aebc-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aebc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aebc-121">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="7aebc-121">See also</span></span>

- [<span data-ttu-id="7aebc-122">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="7aebc-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="7aebc-123">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="7aebc-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="7aebc-124">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="7aebc-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="7aebc-125">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="7aebc-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
