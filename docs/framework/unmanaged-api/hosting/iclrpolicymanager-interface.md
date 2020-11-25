---
title: Интерфейс ICLRPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 7092a1c792fee7f6173dcde211b8e807f6ab02a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725590"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="0e439-102">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0e439-102">ICLRPolicyManager Interface</span></span>

<span data-ttu-id="0e439-103">Предоставляет методы, позволяющие основному приложению указывать действия политики, выполняемые в случае сбоев и истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="0e439-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e439-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0e439-104">Methods</span></span>  
  
|<span data-ttu-id="0e439-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0e439-105">Method</span></span>|<span data-ttu-id="0e439-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0e439-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e439-107">Метод SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="0e439-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="0e439-108">Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="0e439-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="0e439-109">Метод SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="0e439-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="0e439-110">Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.</span><span class="sxs-lookup"><span data-stu-id="0e439-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="0e439-111">Метод SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="0e439-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="0e439-112">Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="0e439-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="0e439-113">Метод SetTimeout</span><span class="sxs-lookup"><span data-stu-id="0e439-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="0e439-114">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="0e439-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="0e439-115">Метод SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="0e439-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="0e439-116">Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении операции.</span><span class="sxs-lookup"><span data-stu-id="0e439-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="0e439-117">Метод SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="0e439-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="0e439-118">Задает поведение среды CLR при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="0e439-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e439-119">Требования</span><span class="sxs-lookup"><span data-stu-id="0e439-119">Requirements</span></span>  

 <span data-ttu-id="0e439-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e439-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e439-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e439-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e439-122">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e439-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e439-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e439-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e439-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e439-124">See also</span></span>

- [<span data-ttu-id="0e439-125">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="0e439-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="0e439-126">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="0e439-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="0e439-127">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="0e439-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="0e439-128">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0e439-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
