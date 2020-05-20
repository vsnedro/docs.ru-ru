---
title: Метод ICLRRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
ms.openlocfilehash: 55cd444ffedc92ba74239421ae548ffd930e6ab7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703933"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="d76b7-102">Метод ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="d76b7-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="d76b7-103">Останавливает выполнение кода средой CLR.</span><span class="sxs-lookup"><span data-stu-id="d76b7-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d76b7-104">Этот метод не освобождает ресурсы для узла, выгружает домены приложений или уничтожает потоки.</span><span class="sxs-lookup"><span data-stu-id="d76b7-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="d76b7-105">Необходимо завершить процесс, чтобы освободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="d76b7-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76b7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d76b7-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d76b7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d76b7-107">Return Value</span></span>  
  
|<span data-ttu-id="d76b7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d76b7-108">HRESULT</span></span>|<span data-ttu-id="d76b7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d76b7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d76b7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d76b7-110">S_OK</span></span>|<span data-ttu-id="d76b7-111">`Stop`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d76b7-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="d76b7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d76b7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d76b7-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d76b7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d76b7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d76b7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d76b7-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d76b7-115">The call timed out.</span></span>|  
|<span data-ttu-id="d76b7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d76b7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d76b7-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d76b7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d76b7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d76b7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d76b7-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d76b7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d76b7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d76b7-120">E_FAIL</span></span>|<span data-ttu-id="d76b7-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d76b7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d76b7-122">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d76b7-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d76b7-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d76b7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d76b7-124">Требования</span><span class="sxs-lookup"><span data-stu-id="d76b7-124">Requirements</span></span>  
 <span data-ttu-id="d76b7-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d76b7-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76b7-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d76b7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d76b7-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d76b7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d76b7-128">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76b7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76b7-129">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="d76b7-129">See also</span></span>

- [<span data-ttu-id="d76b7-130">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d76b7-130">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
