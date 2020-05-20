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
ms.openlocfilehash: 8788d6e2220778a3f0926d5ed3dd59142487bcca
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616194"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="4e308-102">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="4e308-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="4e308-103">Описание действий политики, которые узел может задать для операций, описанных в [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) и ошибках, описанных в [еклрфаилуре](eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4e308-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e308-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e308-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="4e308-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4e308-105">Members</span></span>  
  
|<span data-ttu-id="4e308-106">Член</span><span class="sxs-lookup"><span data-stu-id="4e308-106">Member</span></span>|<span data-ttu-id="4e308-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4e308-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="4e308-108">Указывает, что среда CLR должна корректно прерывать поток.</span><span class="sxs-lookup"><span data-stu-id="4e308-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="4e308-109">Корректное прерывание включает попытки запуска всех `finally` блоков, все `catch` блоки, связанные с пределами потоков и методы завершения.</span><span class="sxs-lookup"><span data-stu-id="4e308-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="4e308-110">Указывает, что среда CLR должна перейти в отключенное состояние.</span><span class="sxs-lookup"><span data-stu-id="4e308-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="4e308-111">В затронутом процессе не может быть выполнен дальнейший управляемый код, и потокам не удастся войти в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="4e308-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="4e308-112">Указывает, что среда CLR должна попытаться корректно выйти из процесса, включая запуск методов завершения и выполнение операций очистки и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="4e308-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="4e308-113">Указывает, что среда CLR должна немедленно выйти из процесса, не запуская методы завершения, а также выполнять операции очистки и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="4e308-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="4e308-114">Однако уведомление отправляется в отладчик.</span><span class="sxs-lookup"><span data-stu-id="4e308-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="4e308-115">Указывает, что никакие действия не следует предпринимать.</span><span class="sxs-lookup"><span data-stu-id="4e308-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="4e308-116">Указывает, что среда CLR должна выполнять грубое прерывание потока.</span><span class="sxs-lookup"><span data-stu-id="4e308-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="4e308-117">Выполняются только `catch` те `finally` блоки и, которые помечены как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4e308-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="4e308-118">Указывает, что среда CLR должна выйти из процесса без запуска методов завершения или ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="4e308-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="4e308-119">Указывает, что среда CLR должна выполнить грубую выгрузку <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="4e308-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="4e308-120">Выполняются только методы завершения, помеченные как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4e308-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="4e308-121">Аналогично, все потоки с этим <xref:System.AppDomain> в стеке получают `ThreadAbortException` , но выполняются только те `catch` блоки и, которые `finally` помечены как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4e308-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="4e308-122">Указывает, что должно быть создано исключение, соответствующее условию, например нехватки памяти, переполнение буфера и т. д.</span><span class="sxs-lookup"><span data-stu-id="4e308-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="4e308-123">Указывает, что <xref:System.AppDomain> необходимо выгрузить.</span><span class="sxs-lookup"><span data-stu-id="4e308-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="4e308-124">Среда CLR пытается запустить методы завершения.</span><span class="sxs-lookup"><span data-stu-id="4e308-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e308-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4e308-125">Remarks</span></span>  
 <span data-ttu-id="4e308-126">Узел задает действия политики, вызывая методы интерфейса [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4e308-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="4e308-127">Сведения о принудительном и корректном аварийном завершении см. в разделе Перечисление [еклроператион](eclroperation-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4e308-127">For information about rude and graceful aborts, see the [EClrOperation](eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e308-128">Требования</span><span class="sxs-lookup"><span data-stu-id="4e308-128">Requirements</span></span>  
 <span data-ttu-id="4e308-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e308-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e308-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e308-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e308-131">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e308-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e308-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e308-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e308-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4e308-133">See also</span></span>

- [<span data-ttu-id="4e308-134">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="4e308-134">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="4e308-135">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4e308-135">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="4e308-136">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4e308-136">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="4e308-137">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="4e308-137">Hosting Enumerations</span></span>](hosting-enumerations.md)
