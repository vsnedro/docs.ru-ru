---
title: Интерфейс IAppDomainBinding
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
ms.openlocfilehash: 652739ad51e0a177f7b0fc6c0c9a11508c820bb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721729"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="f4973-102">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="f4973-102">IAppDomainBinding Interface</span></span>

<span data-ttu-id="f4973-103">Предоставляет метод, вызываемый средой CLR для уведомления ведущего приложения о создании домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f4973-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4973-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f4973-104">Methods</span></span>  
  
|<span data-ttu-id="f4973-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f4973-105">Method</span></span>|<span data-ttu-id="f4973-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f4973-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4973-107">Метод OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="f4973-107">OnAppDomain Method</span></span>](iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="f4973-108">Вызывается средой CLR для уведомления узла о создании домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f4973-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4973-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f4973-109">Requirements</span></span>  

 <span data-ttu-id="f4973-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4973-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4973-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4973-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4973-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4973-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4973-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4973-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4973-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f4973-114">See also</span></span>

- [<span data-ttu-id="f4973-115">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f4973-115">Hosting Interfaces</span></span>](hosting-interfaces.md)
