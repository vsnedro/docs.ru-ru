---
title: Интерфейс ICLRTask2
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: b067ca72e030bce24a7efde5e3488a00024e9613
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762873"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="6f5b6-102">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="6f5b6-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="6f5b6-103">Предоставляет все функциональные возможности интерфейса [ICLRTask](iclrtask-interface.md) ; Кроме того, предоставляет методы, которые позволяют задерживать прерывания потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-103">Provides all the functionality of the [ICLRTask](iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f5b6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6f5b6-104">Methods</span></span>  
  
|<span data-ttu-id="6f5b6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6f5b6-105">Method</span></span>|<span data-ttu-id="6f5b6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6f5b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f5b6-107">Метод BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6f5b6-107">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="6f5b6-108">Откладывает запросы на прерывание нового потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="6f5b6-109">Метод EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6f5b6-109">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="6f5b6-110">Разрешает новые или ожидающие запросы на прерывание потока в результате прерывания потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f5b6-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6f5b6-111">Remarks</span></span>  
 <span data-ttu-id="6f5b6-112">`ICLRTask2`Интерфейс наследует `ICLRTask` интерфейс и добавляет методы, позволяющие узлу откладывать прерывания потока, чтобы защитить область кода, которая не должна завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="6f5b6-113">Вызов `BeginPreventAsyncAbort` увеличивает счетчик прерывания задержки потока для текущего потока и вызывает метод `EndPreventAsyncAbort` декремента.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="6f5b6-114">Вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="6f5b6-115">Пока значение счетчика больше нуля, прерывания потока для текущего потока откладываются.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="6f5b6-116">Если вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` не являются парными, то можно достичь состояния, в котором прерывания потока не могут быть доставлены в текущий поток.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="6f5b6-117">Задержка не учитывается для потока, который прерывает работу.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="6f5b6-118">Функциональные возможности, предоставляемые этой функцией, используются внутри виртуальной машины (ВМ).</span><span class="sxs-lookup"><span data-stu-id="6f5b6-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="6f5b6-119">Неправильное использование этих методов может привести к неопределенному поведению в виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="6f5b6-120">Например, при вызове `EndPreventAsyncAbort` без первого вызова `BeginPreventAsyncAbort` значение счетчика может равняться нулю, когда виртуальная машина ранее увеличила ее.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="6f5b6-121">Аналогично, внутренний счетчик не проверяется на переполнение.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="6f5b6-122">Если он превышает его предельное значение, так как он увеличивается как узлом, так и виртуальной машиной, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="6f5b6-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="6f5b6-123">Сведения о членах, унаследованных от `ICLRTask` и о других применениях этого интерфейса, см. в разделе интерфейс [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6f5b6-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5b6-124">Требования</span><span class="sxs-lookup"><span data-stu-id="6f5b6-124">Requirements</span></span>  
 <span data-ttu-id="6f5b6-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5b6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5b6-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6f5b6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f5b6-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6f5b6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f5b6-128">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5b6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5b6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6f5b6-129">See also</span></span>

- [<span data-ttu-id="6f5b6-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6f5b6-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6f5b6-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6f5b6-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6f5b6-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="6f5b6-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6f5b6-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6f5b6-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6f5b6-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6f5b6-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
