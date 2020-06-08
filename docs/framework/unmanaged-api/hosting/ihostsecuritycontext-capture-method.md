---
title: Метод IHostSecurityContext::Capture
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
ms.openlocfilehash: e1df31ed8b652837a33b360b1378f99e6800cbea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501525"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="b529d-102">Метод IHostSecurityContext::Capture</span><span class="sxs-lookup"><span data-stu-id="b529d-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="b529d-103">Возвращает клон экземпляра [IHostSecurityContext](ihostsecuritycontext-interface.md) , возвращенный из вызова [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="b529d-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b529d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b529d-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b529d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b529d-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="b529d-106">заполняет Указатель на адрес клона `IHostSecurityContext` объекта, который необходимо записать.</span><span class="sxs-lookup"><span data-stu-id="b529d-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b529d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b529d-107">Return Value</span></span>  
  
|<span data-ttu-id="b529d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b529d-108">HRESULT</span></span>|<span data-ttu-id="b529d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b529d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b529d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b529d-110">S_OK</span></span>|<span data-ttu-id="b529d-111">`Capture`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b529d-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="b529d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b529d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b529d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b529d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b529d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b529d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b529d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b529d-115">The call timed out.</span></span>|  
|<span data-ttu-id="b529d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b529d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b529d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b529d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b529d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b529d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b529d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b529d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b529d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b529d-120">E_FAIL</span></span>|<span data-ttu-id="b529d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b529d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b529d-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b529d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b529d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b529d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b529d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b529d-124">Remarks</span></span>  
 <span data-ttu-id="b529d-125">Указатель интерфейса, возвращенный из `Capture` , является клоном захваченного контекста.</span><span class="sxs-lookup"><span data-stu-id="b529d-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="b529d-126">Когда эта информация перемещается по асинхронной кодовой точке, ее время существования отделяется от указателя, на который был сделан вызов.</span><span class="sxs-lookup"><span data-stu-id="b529d-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="b529d-127">Таким образом, исходный указатель может быть освобожден.</span><span class="sxs-lookup"><span data-stu-id="b529d-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b529d-128">Требования</span><span class="sxs-lookup"><span data-stu-id="b529d-128">Requirements</span></span>  
 <span data-ttu-id="b529d-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b529d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b529d-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b529d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b529d-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b529d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b529d-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b529d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b529d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b529d-133">See also</span></span>

- [<span data-ttu-id="b529d-134">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="b529d-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b529d-135">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="b529d-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
