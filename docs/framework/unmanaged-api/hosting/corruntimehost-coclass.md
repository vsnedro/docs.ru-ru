---
title: Компонентный класс CorRuntimeHost
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: cd4e675b4ba50b47146428d204c28cc943c23c69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688007"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="108d1-102">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="108d1-102">CorRuntimeHost Coclass</span></span>

<span data-ttu-id="108d1-103">Предоставляет интерфейсы для управления приложениями, которые выполняются средой CLR.</span><span class="sxs-lookup"><span data-stu-id="108d1-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="108d1-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="108d1-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="108d1-105">Interfaces</span></span>  
  
|<span data-ttu-id="108d1-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="108d1-106">Interface</span></span>|<span data-ttu-id="108d1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="108d1-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="108d1-108">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="108d1-108">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="108d1-109">Предоставляет методы для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="108d1-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="108d1-110">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="108d1-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="108d1-111">Предоставляет методы, позволяющие основному приложению запускать и прекращать работу среды CLR, создавать и настраивать домены приложений, получать доступ к домену по умолчанию и перечислять все домены, выполняющиеся в процессе.</span><span class="sxs-lookup"><span data-stu-id="108d1-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="108d1-112">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="108d1-112">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="108d1-113">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="108d1-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="108d1-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="108d1-114">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="108d1-115">Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="108d1-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="108d1-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="108d1-116">"IValidator"</span></span>|<span data-ttu-id="108d1-117">Предоставляет методы для проверки переносимых исполняемых образов и подробных отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="108d1-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="108d1-118">Требования</span><span class="sxs-lookup"><span data-stu-id="108d1-118">Requirements</span></span>  

 <span data-ttu-id="108d1-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108d1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108d1-120">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="108d1-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="108d1-121">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="108d1-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="108d1-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108d1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108d1-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="108d1-123">See also</span></span>

- [<span data-ttu-id="108d1-124">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="108d1-124">Hosting Coclasses</span></span>](hosting-coclasses.md)
