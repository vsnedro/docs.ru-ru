---
title: Интерфейс IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 9dd89abb332853b966aa81dc506099b7af6ca3b2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804940"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="5803c-102">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="5803c-102">IHostControl Interface</span></span>
<span data-ttu-id="5803c-103">Предоставляет методы для настройки загрузки сборок и для определения того, какие интерфейсы размещения поддерживает узел.</span><span class="sxs-lookup"><span data-stu-id="5803c-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5803c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5803c-104">Methods</span></span>  
  
|<span data-ttu-id="5803c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5803c-105">Method</span></span>|<span data-ttu-id="5803c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5803c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5803c-107">Метод GetHostManager</span><span class="sxs-lookup"><span data-stu-id="5803c-107">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="5803c-108">Возвращает указатель интерфейса на реализацию интерфейса узла с указанным `IID` .</span><span class="sxs-lookup"><span data-stu-id="5803c-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="5803c-109">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="5803c-109">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="5803c-110">Уведомляет узел о том, что домен приложения создан.</span><span class="sxs-lookup"><span data-stu-id="5803c-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5803c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5803c-111">Requirements</span></span>  
 <span data-ttu-id="5803c-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5803c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5803c-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5803c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5803c-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5803c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5803c-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5803c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5803c-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5803c-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="5803c-117">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5803c-117">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="5803c-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5803c-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="5803c-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5803c-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
