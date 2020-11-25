---
title: Перечисление EClrOperation
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: c24e4557695d26666682ee385131abaab707a24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720715"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="8be1b-102">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="8be1b-102">EClrOperation Enumeration</span></span>

<span data-ttu-id="8be1b-103">Описывает набор операций, для которых узел может применять действия политики.</span><span class="sxs-lookup"><span data-stu-id="8be1b-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8be1b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="8be1b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="8be1b-105">Members</span></span>  
  
|<span data-ttu-id="8be1b-106">Член</span><span class="sxs-lookup"><span data-stu-id="8be1b-106">Member</span></span>|<span data-ttu-id="8be1b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8be1b-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="8be1b-108">Узел может указывать действия политики, которые будут выполняться, когда объект <xref:System.AppDomain> выгружается в некорректном (принудительном) режиме.</span><span class="sxs-lookup"><span data-stu-id="8be1b-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="8be1b-109">Узел может указывать действия политики, выполняемые при <xref:System.AppDomain> выгрузке.</span><span class="sxs-lookup"><span data-stu-id="8be1b-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="8be1b-110">Узел может указывать действия политики, выполняемые при выполнении методов завершения.</span><span class="sxs-lookup"><span data-stu-id="8be1b-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="8be1b-111">Узел может указывать действия политики, выполняемые при завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="8be1b-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="8be1b-112">Узел может указывать действия политики, выполняемые при прерывании потока.</span><span class="sxs-lookup"><span data-stu-id="8be1b-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="8be1b-113">Узел может указывать действия политики, выполняемые при выполнении грубого прерывания потока в критической области кода.</span><span class="sxs-lookup"><span data-stu-id="8be1b-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="8be1b-114">Узел может указать действия политики, которые должны выполняться, когда грубое прерывание потока происходит в некритической области кода.</span><span class="sxs-lookup"><span data-stu-id="8be1b-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8be1b-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8be1b-115">Remarks</span></span>  

 <span data-ttu-id="8be1b-116">Инфраструктура надежности среды CLR различает прерывания и сбои выделения ресурсов, происходящие в критических областях кода и происходящих в некритических областях кода.</span><span class="sxs-lookup"><span data-stu-id="8be1b-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="8be1b-117">Это различие состоит в том, что узлы могут задавать разные политики в зависимости от того, где происходит сбой в коде.</span><span class="sxs-lookup"><span data-stu-id="8be1b-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="8be1b-118">*Критическая область кода* — это любое пространство, в котором среда CLR не может гарантировать, что прерывание задачи или невозможность завершения запроса ресурсов повлияет только на текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="8be1b-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="8be1b-119">Например, если задача удерживает блокировку и получает значение HRESULT, которое указывает на сбой при выполнении запроса на выделение памяти, недостаточно просто прервать эту задачу, чтобы обеспечить стабильность <xref:System.AppDomain> , поскольку <xref:System.AppDomain> может содержать другие задачи, ожидающие той же блокировки.</span><span class="sxs-lookup"><span data-stu-id="8be1b-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="8be1b-120">Чтобы отказаться от текущей задачи, может привести к тому, что другие задачи перестанут отвечать на запросы.</span><span class="sxs-lookup"><span data-stu-id="8be1b-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="8be1b-121">В этом случае ведущему приложению требуется возможность выгрузить всю, <xref:System.AppDomain> а не риск потенциально нестабильной работы.</span><span class="sxs-lookup"><span data-stu-id="8be1b-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="8be1b-122">С другой стороны, *некритическая область кода*— это регион, в котором CLR может гарантировать, что прерывание или сбой повлияет только на задачу, на которой возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="8be1b-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="8be1b-123">Среда CLR также различает корректное и некорректное (принудительное) прерывание.</span><span class="sxs-lookup"><span data-stu-id="8be1b-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="8be1b-124">Как правило, обычное или корректное прерывание делает все усилия для выполнения подпрограмм обработки исключений и методов завершения перед прерыванием задачи, в то время как грубое прерывание не делает таких гарантий.</span><span class="sxs-lookup"><span data-stu-id="8be1b-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be1b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="8be1b-125">Requirements</span></span>  

 <span data-ttu-id="8be1b-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be1b-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be1b-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8be1b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8be1b-128">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8be1b-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8be1b-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be1b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be1b-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8be1b-130">See also</span></span>

- [<span data-ttu-id="8be1b-131">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="8be1b-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="8be1b-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="8be1b-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="8be1b-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="8be1b-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="8be1b-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="8be1b-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="8be1b-135">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="8be1b-135">Hosting Enumerations</span></span>](hosting-enumerations.md)
