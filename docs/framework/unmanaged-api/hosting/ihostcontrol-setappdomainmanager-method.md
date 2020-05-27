---
title: Метод IHostControl::SetAppDomainManager
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: 74ffc5c92402808ae566d7cb014d9d920c384ae8
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804934"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="d8b4a-102">Метод IHostControl::SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="d8b4a-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="d8b4a-103">Уведомляет узел о том, что домен приложения создан.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8b4a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8b4a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8b4a-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="d8b4a-106">окне Числовой идентификатор выбранного объекта <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="d8b4a-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="d8b4a-107">окне Указатель на <xref:System.AppDomainManager> объект, который реализуется узлом как `IUnknown` .</span><span class="sxs-lookup"><span data-stu-id="d8b4a-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8b4a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d8b4a-108">Return Value</span></span>  
  
|<span data-ttu-id="d8b4a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8b4a-109">HRESULT</span></span>|<span data-ttu-id="d8b4a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d8b4a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8b4a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8b4a-111">S_OK</span></span>|<span data-ttu-id="d8b4a-112">`SetAppDomainManager`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="d8b4a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8b4a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8b4a-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8b4a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8b4a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8b4a-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-116">The call timed out.</span></span>|  
|<span data-ttu-id="d8b4a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8b4a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8b4a-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8b4a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8b4a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8b4a-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8b4a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8b4a-121">E_FAIL</span></span>|<span data-ttu-id="d8b4a-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8b4a-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8b4a-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b4a-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="d8b4a-125">Remarks</span></span>  
 <span data-ttu-id="d8b4a-126"><xref:System.AppDomainManager>Предоставляет ведущему приложению механизм для начальной загрузки в управляемый код и управления созданием и параметрами каждого из них <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="d8b4a-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="d8b4a-127">Объект <xref:System.AppDomainManager> загружается в каждый <xref:System.AppDomain> при <xref:System.AppDomain> создании.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="d8b4a-128">Если он выбран, среда CLR уведомляет узел о том, что домен приложения был создан, задав значение `pUnkAppDomainManager` параметра.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="d8b4a-129">В своей реализации `SetAppDomainManager` метода узел может задать имя и тип сборки для диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d8b4a-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8b4a-130">Требования</span><span class="sxs-lookup"><span data-stu-id="d8b4a-130">Requirements</span></span>  
 <span data-ttu-id="d8b4a-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8b4a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8b4a-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d8b4a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8b4a-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8b4a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8b4a-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8b4a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b4a-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d8b4a-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="d8b4a-136">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="d8b4a-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
