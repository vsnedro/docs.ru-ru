---
title: Интерфейс IHostTask
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 1b7209a36f8e9d6f02bd4cc1882adeef8af30c3d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503934"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="80bb8-102">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="80bb8-102">IHostTask Interface</span></span>
<span data-ttu-id="80bb8-103">Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="80bb8-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80bb8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="80bb8-104">Methods</span></span>  
  
|<span data-ttu-id="80bb8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="80bb8-105">Method</span></span>|<span data-ttu-id="80bb8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="80bb8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80bb8-107">Метод Alert</span><span class="sxs-lookup"><span data-stu-id="80bb8-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="80bb8-108">Запрашивает выход узла из задачи, представленной текущим `IHostTask` экземпляром, поэтому задачу можно прервать.</span><span class="sxs-lookup"><span data-stu-id="80bb8-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="80bb8-109">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="80bb8-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="80bb8-110">Возвращает уровень приоритета потока задачи, представленной текущим `IHostTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="80bb8-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="80bb8-111">Метод Join</span><span class="sxs-lookup"><span data-stu-id="80bb8-111">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="80bb8-112">Блокирует вызывающую задачу до тех пор, пока задача, представленная текущим `IHostTask` экземпляром, не завершится, истечет указанный интервал времени, или будет вызван метод [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="80bb8-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="80bb8-113">Метод SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="80bb8-113">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="80bb8-114">Связывает экземпляр [интерфейса ICLRTask](iclrtask-interface.md) с текущим `IHostTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="80bb8-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="80bb8-115">Метод SetPriority</span><span class="sxs-lookup"><span data-stu-id="80bb8-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="80bb8-116">Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим `IHostTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="80bb8-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="80bb8-117">Метод Start</span><span class="sxs-lookup"><span data-stu-id="80bb8-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="80bb8-118">Запрашивает, что узел перемещает задачу, представленную текущим `IHostTask` экземпляром, из приостановленного состояния в активное состояние, в котором может выполняться код.</span><span class="sxs-lookup"><span data-stu-id="80bb8-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80bb8-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="80bb8-119">Remarks</span></span>  
 <span data-ttu-id="80bb8-120">Среда CLR вызывает методы, определенные `IHostTask` для запуска задачи, установки ее уровня приоритета и т. д.</span><span class="sxs-lookup"><span data-stu-id="80bb8-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80bb8-121">Требования</span><span class="sxs-lookup"><span data-stu-id="80bb8-121">Requirements</span></span>  
 <span data-ttu-id="80bb8-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80bb8-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80bb8-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="80bb8-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80bb8-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="80bb8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80bb8-125">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80bb8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80bb8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="80bb8-126">See also</span></span>

- [<span data-ttu-id="80bb8-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="80bb8-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="80bb8-128">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="80bb8-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="80bb8-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="80bb8-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="80bb8-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="80bb8-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
