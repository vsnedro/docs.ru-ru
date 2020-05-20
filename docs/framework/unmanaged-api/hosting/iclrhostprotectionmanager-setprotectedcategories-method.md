---
title: Метод ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: 5cf6f942add3d090cf830e71a545b9f4d4f69f00
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703164"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="fd0b9-102">Метод ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="fd0b9-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="fd0b9-103">Указывает, какие категории управляемых типов и членов следует блокировать при выполнении в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd0b9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd0b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd0b9-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="fd0b9-106">окне Сочетание значений [еапикатегориес](eapicategories-enumeration.md) , указывающих, какие категории управляемых типов и членов должны блокироваться в коде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-106">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd0b9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd0b9-107">Return Value</span></span>  
  
|<span data-ttu-id="fd0b9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd0b9-108">HRESULT</span></span>|<span data-ttu-id="fd0b9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fd0b9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd0b9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd0b9-110">S_OK</span></span>|<span data-ttu-id="fd0b9-111">`SetProtectedCategories`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="fd0b9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd0b9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd0b9-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd0b9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd0b9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd0b9-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd0b9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd0b9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd0b9-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd0b9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd0b9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd0b9-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd0b9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd0b9-120">E_FAIL</span></span>|<span data-ttu-id="fd0b9-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd0b9-122">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd0b9-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0b9-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fd0b9-124">Remarks</span></span>  
 <span data-ttu-id="fd0b9-125">Каждое `EApiCategories` значение ссылается на список управляемых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="fd0b9-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="fd0b9-126">`EApiCategories`Перечисление и `SetProtectedCategories` метод напрямую связаны с управляемым <xref:System.Security.Permissions.HostProtectionAttribute> классом, который используется для пометки управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описанным в `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="fd0b9-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="fd0b9-127">Дополнительные сведения см <xref:System.Security.Permissions.HostProtectionAttribute> . в разделе и <xref:System.Security.Permissions.HostProtectionResource> перечисление, которое непосредственно соответствует `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="fd0b9-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0b9-128">Требования</span><span class="sxs-lookup"><span data-stu-id="fd0b9-128">Requirements</span></span>  
 <span data-ttu-id="fd0b9-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0b9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0b9-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd0b9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd0b9-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd0b9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd0b9-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0b9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0b9-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fd0b9-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="fd0b9-134">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="fd0b9-134">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="fd0b9-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fd0b9-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="fd0b9-136">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="fd0b9-136">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
