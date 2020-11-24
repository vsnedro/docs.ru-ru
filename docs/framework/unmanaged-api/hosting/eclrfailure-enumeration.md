---
title: Перечисление EClrFailure
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
ms.openlocfilehash: d2794b53ed17640413928b3af0d1ed3656e25f22
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675767"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="78197-102">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="78197-102">EClrFailure Enumeration</span></span>

<span data-ttu-id="78197-103">Описывает набор сбоев, для которых узел может задавать действия политики.</span><span class="sxs-lookup"><span data-stu-id="78197-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78197-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78197-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="78197-105">Члены</span><span class="sxs-lookup"><span data-stu-id="78197-105">Members</span></span>  
  
|<span data-ttu-id="78197-106">Член</span><span class="sxs-lookup"><span data-stu-id="78197-106">Member</span></span>|<span data-ttu-id="78197-107">Описание</span><span class="sxs-lookup"><span data-stu-id="78197-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="78197-108">Произошла ошибка при попытке выделения ресурса (например, потока, блока памяти или блокировки) в некритической области кода.</span><span class="sxs-lookup"><span data-stu-id="78197-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="78197-109">Произошла ошибка при попытке выделения ресурса (например, потока, блока памяти или блокировки) в критической области кода.</span><span class="sxs-lookup"><span data-stu-id="78197-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="78197-110">Общеязыковая среда выполнения (CLR) больше не может выполнять управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="78197-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="78197-111">Исходя этого, вызовы любых функций размещения возвращают значение HRESULT, равное HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="78197-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="78197-112">Потоку не удалось снять блокировку после возврата из <xref:System.AppDomain> объекта.</span><span class="sxs-lookup"><span data-stu-id="78197-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="78197-113">Узлу не удается установить этот сбой, чтобы привести к прерыванию потока.</span><span class="sxs-lookup"><span data-stu-id="78197-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="78197-114">Произошло переполнение стека.</span><span class="sxs-lookup"><span data-stu-id="78197-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="78197-115">Предпринята попытка чтения или записи в защищенную память.</span><span class="sxs-lookup"><span data-stu-id="78197-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="78197-116">Не поддерживается в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="78197-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="78197-117">Ошибка контракта кода.</span><span class="sxs-lookup"><span data-stu-id="78197-117">A code contract failure occurred.</span></span> <span data-ttu-id="78197-118">См. раздел [контракты кода](../../debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="78197-118">See [Code Contracts](../../debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78197-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="78197-119">Remarks</span></span>  

 <span data-ttu-id="78197-120">Список значений [еполициактион](epolicyaction-enumeration.md) , которые узел может использовать для указания действий политики для условий сбоя, см. в описании метода [ICLRPolicyManager:: сетактиононфаилуре](iclrpolicymanager-setactiononfailure-method.md) .</span><span class="sxs-lookup"><span data-stu-id="78197-120">See the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="78197-121">Дополнительные сведения о критических и некритических областях кода см. в разделе [еклроператион](eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="78197-121">For more information about critical and non-critical regions of code, see [EClrOperation](eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78197-122">Требования</span><span class="sxs-lookup"><span data-stu-id="78197-122">Requirements</span></span>  

 <span data-ttu-id="78197-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78197-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78197-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="78197-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78197-125">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78197-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78197-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78197-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78197-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="78197-127">See also</span></span>

- [<span data-ttu-id="78197-128">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="78197-128">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="78197-129">Метод SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="78197-129">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="78197-130">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="78197-130">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="78197-131">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="78197-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
