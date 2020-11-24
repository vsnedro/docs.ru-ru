---
title: Метод ICLRControl::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: 28fdd5340aee0fcd9875dd983c8c7649b5491c04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674714"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="5dc0b-102">Метод ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="5dc0b-102">ICLRControl::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="5dc0b-103">Задает тип, производный от <xref:System.AppDomainManager> типа для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5dc0b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dc0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5dc0b-105">Parameters</span></span>  

 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="5dc0b-106">окне Имя сборки, в которой реализован запрошенный тип, производный от <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="5dc0b-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="5dc0b-107">окне Имя типа, реализованного в `pwzAppDomainManagerAssembly` параметре, который реализует возможности <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="5dc0b-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dc0b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5dc0b-108">Return Value</span></span>  
  
|<span data-ttu-id="5dc0b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5dc0b-109">HRESULT</span></span>|<span data-ttu-id="5dc0b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="5dc0b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5dc0b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5dc0b-111">S_OK</span></span>|<span data-ttu-id="5dc0b-112">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="5dc0b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5dc0b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5dc0b-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5dc0b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5dc0b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5dc0b-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-116">The call timed out.</span></span>|  
|<span data-ttu-id="5dc0b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5dc0b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5dc0b-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5dc0b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5dc0b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5dc0b-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5dc0b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5dc0b-121">E_FAIL</span></span>|<span data-ttu-id="5dc0b-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5dc0b-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5dc0b-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5dc0b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5dc0b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="5dc0b-125">Requirements</span></span>  

 <span data-ttu-id="5dc0b-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc0b-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc0b-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5dc0b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5dc0b-128">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5dc0b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dc0b-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc0b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc0b-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5dc0b-130">See also</span></span>

- [<span data-ttu-id="5dc0b-131">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5dc0b-131">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="5dc0b-132">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="5dc0b-132">IHostControl Interface</span></span>](ihostcontrol-interface.md)
