---
title: Метод ICLRTask2::EndPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 3ea36c56ef9ccf5886ba96191627e5283da186f7
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762858"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="1be95-102">Метод ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="1be95-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="1be95-103">Разрешает новые или ожидающие запросы на прерывание потока в результате прерывания потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="1be95-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1be95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1be95-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1be95-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1be95-105">Return Value</span></span>  
 <span data-ttu-id="1be95-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="1be95-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1be95-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1be95-107">HRESULT</span></span>|<span data-ttu-id="1be95-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1be95-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1be95-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="1be95-109">S_OK</span></span>|<span data-ttu-id="1be95-110">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="1be95-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="1be95-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1be95-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1be95-112">Метод был вызван в потоке, который не является текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="1be95-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be95-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1be95-113">Remarks</span></span>  
 <span data-ttu-id="1be95-114">При вызове этого метода счетчик "задержка — прерывание потока" для текущего потока уменьшается на один.</span><span class="sxs-lookup"><span data-stu-id="1be95-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="1be95-115">Вызовы [ICLRTask2:: BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) и `EndPreventAsyncAbort` могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="1be95-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="1be95-116">Пока значение счетчика больше нуля, прерывания потока для текущего потока откладываются.</span><span class="sxs-lookup"><span data-stu-id="1be95-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="1be95-117">Функциональные возможности, предоставляемые этой функцией, используются внутри виртуальной машины (ВМ).</span><span class="sxs-lookup"><span data-stu-id="1be95-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="1be95-118">Неправильное использование этих методов может привести к неопределенному поведению в виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="1be95-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="1be95-119">Например, при вызове `EndPreventAsyncAbort` без первого вызова `BeginPreventAsyncAbort` значение счетчика может равняться нулю, когда виртуальная машина ранее увеличила ее.</span><span class="sxs-lookup"><span data-stu-id="1be95-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="1be95-120">Аналогично, внутренний счетчик не проверяется на переполнение.</span><span class="sxs-lookup"><span data-stu-id="1be95-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="1be95-121">Если он превышает его предельное значение, так как он увеличивается как узлом, так и виртуальной машиной, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="1be95-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be95-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1be95-122">Requirements</span></span>  
 <span data-ttu-id="1be95-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1be95-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be95-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1be95-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1be95-125">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1be95-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1be95-126">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be95-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be95-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1be95-127">See also</span></span>

- [<span data-ttu-id="1be95-128">Метод BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="1be95-128">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="1be95-129">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="1be95-129">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="1be95-130">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1be95-130">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1be95-131">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="1be95-131">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1be95-132">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1be95-132">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="1be95-133">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1be95-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
