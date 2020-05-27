---
title: Метод IHostSecurityManager::SetThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: 7891ddc5085eedd2a9010023f119d08f101e2fa3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803779"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="99e65-102">Метод IHostSecurityManager::SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="99e65-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="99e65-103">Задает обработчик для текущего выполняющегося потока.</span><span class="sxs-lookup"><span data-stu-id="99e65-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99e65-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99e65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99e65-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="99e65-106">окне Маркер, который задается для выполняемого в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="99e65-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99e65-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99e65-107">Return Value</span></span>  
  
|<span data-ttu-id="99e65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99e65-108">HRESULT</span></span>|<span data-ttu-id="99e65-109">Описание</span><span class="sxs-lookup"><span data-stu-id="99e65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99e65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="99e65-110">S_OK</span></span>|<span data-ttu-id="99e65-111">`SetThreadToken`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="99e65-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="99e65-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99e65-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99e65-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="99e65-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99e65-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99e65-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99e65-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="99e65-115">The call timed out.</span></span>|  
|<span data-ttu-id="99e65-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99e65-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99e65-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="99e65-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99e65-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99e65-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99e65-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="99e65-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99e65-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99e65-120">E_FAIL</span></span>|<span data-ttu-id="99e65-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="99e65-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99e65-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="99e65-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99e65-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="99e65-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e65-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="99e65-124">Remarks</span></span>  
 <span data-ttu-id="99e65-125">`IHostSecurityManager::SetThreadToken`ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция Win32 позволяет вызывающему объекту передать маркер произвольному потоку, в то время как он `IHostSecurityManager::SetThreadToken` может связать маркер только с текущим выполняющимся потоком.</span><span class="sxs-lookup"><span data-stu-id="99e65-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="99e65-126">`HANDLE`Тип не совместим с COM, то есть его размер зависит от операционной системы и требует настраиваемого маршалирования.</span><span class="sxs-lookup"><span data-stu-id="99e65-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="99e65-127">Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.</span><span class="sxs-lookup"><span data-stu-id="99e65-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99e65-128">Требования</span><span class="sxs-lookup"><span data-stu-id="99e65-128">Requirements</span></span>  
 <span data-ttu-id="99e65-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99e65-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e65-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99e65-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99e65-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="99e65-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99e65-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99e65-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e65-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="99e65-133">See also</span></span>

- [<span data-ttu-id="99e65-134">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="99e65-134">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="99e65-135">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="99e65-135">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
