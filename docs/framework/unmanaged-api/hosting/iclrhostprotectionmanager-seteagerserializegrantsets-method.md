---
title: Метод ICLRHostProtectionManager::SetEagerSerializeGrantSets
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
ms.openlocfilehash: 9ce4a5e042e838da8e9eba614f26e35b38af56c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714137"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="da993-102">Метод ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="da993-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>

<span data-ttu-id="da993-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="da993-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da993-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da993-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="da993-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="da993-105">Return Value</span></span>  
  
|<span data-ttu-id="da993-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da993-106">HRESULT</span></span>|<span data-ttu-id="da993-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="da993-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da993-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="da993-108">S_OK</span></span>|<span data-ttu-id="da993-109">`SetEagerSerializeGrantSets` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="da993-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="da993-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da993-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da993-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="da993-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da993-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da993-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da993-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="da993-113">The call timed out.</span></span>|  
|<span data-ttu-id="da993-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da993-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da993-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="da993-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da993-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da993-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da993-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="da993-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da993-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da993-118">E_FAIL</span></span>|<span data-ttu-id="da993-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="da993-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da993-120">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="da993-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da993-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="da993-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da993-122">Требования</span><span class="sxs-lookup"><span data-stu-id="da993-122">Requirements</span></span>  

 <span data-ttu-id="da993-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da993-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da993-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="da993-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da993-125">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da993-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da993-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da993-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da993-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="da993-127">See also</span></span>

- [<span data-ttu-id="da993-128">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="da993-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="da993-129">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="da993-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
