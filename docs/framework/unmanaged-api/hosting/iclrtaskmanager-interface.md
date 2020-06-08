---
title: Интерфейс ICLRTaskManager
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: f918d4e7b95922734d70ed832581e6c494c70b05
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501642"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="e5a8b-102">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e5a8b-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="e5a8b-103">Предоставляет методы, позволяющие узлу явно запрашивать, что среда CLR создает новую задачу, получает выполняемую в данный момент задачу и задает язык и региональные параметры для задачи.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5a8b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e5a8b-104">Methods</span></span>  
  
|<span data-ttu-id="e5a8b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e5a8b-105">Method</span></span>|<span data-ttu-id="e5a8b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e5a8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5a8b-107">Метод CreateTask</span><span class="sxs-lookup"><span data-stu-id="e5a8b-107">CreateTask Method</span></span>](iclrtaskmanager-createtask-method.md)|<span data-ttu-id="e5a8b-108">Явно запрашивает, что среда CLR создает новый экземпляр [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e5a8b-108">Requests explicitly that the CLR create a new [ICLRTask](iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="e5a8b-109">Метод GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="e5a8b-109">GetCurrentTask Method</span></span>](iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="e5a8b-110">Возвращает `ICLRTask` экземпляр, представляющий выполняемую в данный момент задачу.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="e5a8b-111">Метод GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="e5a8b-111">GetCurrentTaskType Method</span></span>](iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="e5a8b-112">Возвращает тип выполняемой в данный момент задачи.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="e5a8b-113">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="e5a8b-113">SetLocale Method</span></span>](iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="e5a8b-114">Уведомляет среду CLR о том, что узел изменил идентификатор локали в выполняющейся задаче.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="e5a8b-115">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="e5a8b-115">SetUILocale Method</span></span>](iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="e5a8b-116">Уведомляет среду CLR о том, что узел изменил идентификатор локали пользовательского интерфейса для выполняемой в данный момент задачи.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a8b-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5a8b-117">Remarks</span></span>  
 <span data-ttu-id="e5a8b-118">Каждая задача, выполняемая в среде размещения, имеет представления на стороне размещения (экземпляр [IHostTask](ihosttask-interface.md)) и на стороне среды CLR (экземпляре [ICLRTask](iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="e5a8b-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](iclrtask-interface.md)).</span></span> <span data-ttu-id="e5a8b-119">Приложение или среда CLR могут инициировать создание задачи, но представление на стороне главного приложения должно быть связано с соответствующим представлением на стороне среды CLR для обеспечения успешной связи между узлом и средой CLR, относящейся к задаче.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="e5a8b-120">Перед выполнением управляемого кода в потоке операционной системы необходимо создать и создать экземпляры этих двух объектов.</span><span class="sxs-lookup"><span data-stu-id="e5a8b-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a8b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e5a8b-121">Requirements</span></span>  
 <span data-ttu-id="e5a8b-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5a8b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a8b-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e5a8b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5a8b-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e5a8b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5a8b-125">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a8b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a8b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e5a8b-126">See also</span></span>

- [<span data-ttu-id="e5a8b-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e5a8b-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e5a8b-128">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="e5a8b-128">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e5a8b-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e5a8b-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="e5a8b-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e5a8b-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
