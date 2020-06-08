---
title: Интерфейс IHostSecurityManager
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 237fe23493460df77a79ba3aed9f0a809cd8aa23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501473"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="33cfc-102">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="33cfc-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="33cfc-103">Предоставляет методы, позволяющие получить доступ к контексту безопасности выполняющегося потока и управлять им.</span><span class="sxs-lookup"><span data-stu-id="33cfc-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33cfc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="33cfc-104">Methods</span></span>  
  
|<span data-ttu-id="33cfc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="33cfc-105">Method</span></span>|<span data-ttu-id="33cfc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="33cfc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33cfc-107">Метод GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="33cfc-107">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="33cfc-108">Возвращает запрошенный [IHostSecurityContext](ihostsecuritycontext-interface.md) из узла.</span><span class="sxs-lookup"><span data-stu-id="33cfc-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="33cfc-109">Метод ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="33cfc-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="33cfc-110">Запрашивает выполнение кода с использованием учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="33cfc-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="33cfc-111">Метод OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="33cfc-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="33cfc-112">Открывает маркер доступа на уровне пользователей, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="33cfc-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="33cfc-113">Метод RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="33cfc-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="33cfc-114">Завершает олицетворение текущего удостоверения пользователя и возвращает исходный маркер потока.</span><span class="sxs-lookup"><span data-stu-id="33cfc-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="33cfc-115">Метод SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="33cfc-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="33cfc-116">Задает контекст безопасности для выполняющегося в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="33cfc-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="33cfc-117">Метод SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="33cfc-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="33cfc-118">Задает обработчик для текущего выполняющегося потока.</span><span class="sxs-lookup"><span data-stu-id="33cfc-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33cfc-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="33cfc-119">Remarks</span></span>  
 <span data-ttu-id="33cfc-120">Узел может управлять доступом кода к маркерам потоков как средой CLR, так и кодом пользователя.</span><span class="sxs-lookup"><span data-stu-id="33cfc-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="33cfc-121">Он также может гарантировать, что полные сведения о контексте безопасности передаются по асинхронным операциям или кодовым точкам с ограниченным доступом к коду.</span><span class="sxs-lookup"><span data-stu-id="33cfc-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="33cfc-122">`IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, которые непрозрачны для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="33cfc-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="33cfc-123">Среда CLR внутренне обрабатывает контекст управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="33cfc-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="33cfc-124">Он запрашивает особенности конкретного процесса `IHostSecurityManager` в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="33cfc-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="33cfc-125">В потоке метода завершения во время выполнения метода завершения.</span><span class="sxs-lookup"><span data-stu-id="33cfc-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="33cfc-126">Во время выполнения конструктора класса и модуля.</span><span class="sxs-lookup"><span data-stu-id="33cfc-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="33cfc-127">В асинхронных точках в рабочем потоке при вызове метода [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33cfc-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="33cfc-128">При обслуживании портов завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="33cfc-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cfc-129">Требования</span><span class="sxs-lookup"><span data-stu-id="33cfc-129">Requirements</span></span>  
 <span data-ttu-id="33cfc-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33cfc-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33cfc-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="33cfc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33cfc-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="33cfc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33cfc-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33cfc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cfc-134">См. также</span><span class="sxs-lookup"><span data-stu-id="33cfc-134">See also</span></span>

- [<span data-ttu-id="33cfc-135">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="33cfc-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="33cfc-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="33cfc-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
