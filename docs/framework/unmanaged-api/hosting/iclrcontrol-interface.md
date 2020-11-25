---
title: Интерфейс ICLRControl
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: acf449014f5bf5683d5488f8ed2ead963676fe6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728346"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="38c59-102">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="38c59-102">ICLRControl Interface</span></span>

<span data-ttu-id="38c59-103">Предоставляет методы, позволяющие узлу получать ссылки и настраивать аспекты среды CLR.</span><span class="sxs-lookup"><span data-stu-id="38c59-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38c59-104">Методы</span><span class="sxs-lookup"><span data-stu-id="38c59-104">Methods</span></span>  
  
|<span data-ttu-id="38c59-105">Метод</span><span class="sxs-lookup"><span data-stu-id="38c59-105">Method</span></span>|<span data-ttu-id="38c59-106">Описание</span><span class="sxs-lookup"><span data-stu-id="38c59-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38c59-107">Метод GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="38c59-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="38c59-108">Возвращает указатель интерфейса на экземпляр любого из типов диспетчера, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="38c59-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="38c59-109">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="38c59-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="38c59-110">Задает тип, производный от <xref:System.AppDomainManager> типа для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="38c59-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38c59-111">Требования</span><span class="sxs-lookup"><span data-stu-id="38c59-111">Requirements</span></span>  

 <span data-ttu-id="38c59-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38c59-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c59-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="38c59-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38c59-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38c59-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38c59-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c59-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c59-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="38c59-116">See also</span></span>

- [<span data-ttu-id="38c59-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="38c59-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="38c59-118">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="38c59-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="38c59-119">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="38c59-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="38c59-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="38c59-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="38c59-121">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="38c59-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="38c59-122">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="38c59-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="38c59-123">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="38c59-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="38c59-124">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="38c59-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="38c59-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="38c59-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
