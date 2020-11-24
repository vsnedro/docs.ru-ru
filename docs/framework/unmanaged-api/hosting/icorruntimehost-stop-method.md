---
title: Метод ICorRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
ms.openlocfilehash: 9342233317535ebecbcddea48b9029b81868eb0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690152"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="fcaf6-102">Метод ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="fcaf6-102">ICorRuntimeHost::Stop Method</span></span>

<span data-ttu-id="fcaf6-103">Останавливает выполнение кода в среде выполнения для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcaf6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcaf6-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fcaf6-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fcaf6-105">Return Value</span></span>  
  
|<span data-ttu-id="fcaf6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fcaf6-106">HRESULT</span></span>|<span data-ttu-id="fcaf6-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="fcaf6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fcaf6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcaf6-108">S_OK</span></span>|<span data-ttu-id="fcaf6-109">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-109">The operation was successful.</span></span>|  
|<span data-ttu-id="fcaf6-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fcaf6-110">S_FALSE</span></span>|<span data-ttu-id="fcaf6-111">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fcaf6-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fcaf6-112">E_FAIL</span></span>|<span data-ttu-id="fcaf6-113">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fcaf6-114">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fcaf6-115">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fcaf6-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fcaf6-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fcaf6-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcaf6-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fcaf6-118">Remarks</span></span>  

 <span data-ttu-id="fcaf6-119">Как правило, вызов метода не требуется `Stop` , поскольку код прекращает выполнение при завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcaf6-120">После вызова `Stop` Среда CLR не может быть инициализирована в том же процессе.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcaf6-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fcaf6-121">Requirements</span></span>  

 <span data-ttu-id="fcaf6-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcaf6-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcaf6-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fcaf6-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcaf6-124">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fcaf6-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcaf6-125">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="fcaf6-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcaf6-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fcaf6-126">See also</span></span>

- [<span data-ttu-id="fcaf6-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="fcaf6-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
