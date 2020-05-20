---
title: Метод ICLRRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: e5ed1cbb640e760d75e1722871453a0bec283bde
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703912"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="deb64-102">Метод ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="deb64-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="deb64-103">Инициализирует среду CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="deb64-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="deb64-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="deb64-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="deb64-105">Return Value</span></span>  
  
|<span data-ttu-id="deb64-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="deb64-106">HRESULT</span></span>|<span data-ttu-id="deb64-107">Описание</span><span class="sxs-lookup"><span data-stu-id="deb64-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="deb64-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="deb64-108">S_OK</span></span>|<span data-ttu-id="deb64-109">`Start`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="deb64-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="deb64-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="deb64-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="deb64-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="deb64-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="deb64-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="deb64-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="deb64-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="deb64-113">The call timed out.</span></span>|  
|<span data-ttu-id="deb64-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="deb64-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="deb64-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="deb64-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="deb64-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="deb64-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="deb64-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="deb64-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="deb64-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="deb64-118">E_FAIL</span></span>|<span data-ttu-id="deb64-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="deb64-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="deb64-120">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="deb64-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="deb64-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="deb64-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="deb64-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="deb64-122">Remarks</span></span>  
 <span data-ttu-id="deb64-123">Во многих случаях нет необходимости вызывать `Start` , так как среда выполнения инициализирует себя автоматически при первом запросе на выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="deb64-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="deb64-124">Однако можно использовать, `Start` чтобы точно указать, когда должна быть инициализирована среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="deb64-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb64-125">Требования</span><span class="sxs-lookup"><span data-stu-id="deb64-125">Requirements</span></span>  
 <span data-ttu-id="deb64-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deb64-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb64-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="deb64-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="deb64-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="deb64-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="deb64-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb64-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb64-130">См. также статью</span><span class="sxs-lookup"><span data-stu-id="deb64-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="deb64-131">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="deb64-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
