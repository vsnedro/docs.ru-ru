---
title: Перечисление EPolicyAction
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: 901c62e6f2519fc4f9251f348c77b11bbe0992be
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504349"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="27ecc-102">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="27ecc-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="27ecc-103">Описание действий политики, которые узел может задать для операций, описанных в [еклроператион](eclroperation-enumeration.md) и ошибках, описанных в [еклрфаилуре](eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="27ecc-103">Describes the policy actions the host can set for operations described by [EClrOperation](eclroperation-enumeration.md) and failures described by [EClrFailure](eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ecc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27ecc-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="27ecc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="27ecc-105">Members</span></span>  
  
|<span data-ttu-id="27ecc-106">Член</span><span class="sxs-lookup"><span data-stu-id="27ecc-106">Member</span></span>|<span data-ttu-id="27ecc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="27ecc-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="27ecc-108">Указывает, что среда CLR должна корректно прерывать поток.</span><span class="sxs-lookup"><span data-stu-id="27ecc-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="27ecc-109">Корректное прерывание включает попытки запуска всех `finally` блоков, все `catch` блоки, связанные с пределами потоков и методы завершения.</span><span class="sxs-lookup"><span data-stu-id="27ecc-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="27ecc-110">Указывает, что среда CLR должна перейти в отключенное состояние.</span><span class="sxs-lookup"><span data-stu-id="27ecc-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="27ecc-111">В затронутом процессе не может быть выполнен дальнейший управляемый код, и потокам не удастся войти в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="27ecc-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="27ecc-112">Указывает, что среда CLR должна попытаться корректно выйти из процесса, включая запуск методов завершения и выполнение операций очистки и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="27ecc-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="27ecc-113">Указывает, что среда CLR должна немедленно выйти из процесса, не запуская методы завершения, а также выполнять операции очистки и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="27ecc-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="27ecc-114">Однако уведомление отправляется в отладчик.</span><span class="sxs-lookup"><span data-stu-id="27ecc-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="27ecc-115">Указывает, что никакие действия не следует предпринимать.</span><span class="sxs-lookup"><span data-stu-id="27ecc-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="27ecc-116">Указывает, что среда CLR должна выполнять грубое прерывание потока.</span><span class="sxs-lookup"><span data-stu-id="27ecc-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="27ecc-117">Выполняются только `catch` те `finally` блоки и, которые помечены как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="27ecc-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="27ecc-118">Указывает, что среда CLR должна выйти из процесса без запуска методов завершения или ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="27ecc-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="27ecc-119">Указывает, что среда CLR должна выполнить грубую выгрузку <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="27ecc-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="27ecc-120">Выполняются только методы завершения, помеченные как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="27ecc-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="27ecc-121">Аналогично, все потоки с этим <xref:System.AppDomain> в стеке получают `ThreadAbortException` , но выполняются только те `catch` блоки и, которые `finally` помечены как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="27ecc-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="27ecc-122">Указывает, что должно быть создано исключение, соответствующее условию, например нехватки памяти, переполнение буфера и т. д.</span><span class="sxs-lookup"><span data-stu-id="27ecc-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="27ecc-123">Указывает, что <xref:System.AppDomain> необходимо выгрузить.</span><span class="sxs-lookup"><span data-stu-id="27ecc-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="27ecc-124">Среда CLR пытается запустить методы завершения.</span><span class="sxs-lookup"><span data-stu-id="27ecc-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27ecc-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="27ecc-125">Remarks</span></span>  
 <span data-ttu-id="27ecc-126">Узел задает действия политики, вызывая методы интерфейса [ICLRPolicyManager](iclrpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="27ecc-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="27ecc-127">Сведения о принудительном и корректном аварийном завершении см. в разделе Перечисление [еклроператион](eclroperation-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="27ecc-127">For information about rude and graceful aborts, see the [EClrOperation](eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27ecc-128">Требования</span><span class="sxs-lookup"><span data-stu-id="27ecc-128">Requirements</span></span>  
 <span data-ttu-id="27ecc-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27ecc-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27ecc-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27ecc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27ecc-131">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="27ecc-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27ecc-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27ecc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ecc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="27ecc-133">See also</span></span>

- [<span data-ttu-id="27ecc-134">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="27ecc-134">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="27ecc-135">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="27ecc-135">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="27ecc-136">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="27ecc-136">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="27ecc-137">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="27ecc-137">Hosting Enumerations</span></span>](hosting-enumerations.md)
