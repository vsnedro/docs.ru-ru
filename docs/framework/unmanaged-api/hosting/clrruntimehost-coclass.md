---
title: Кокласс CLRRuntimeHost
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: 7c77cb2e89cb8fd87bf219780b9460649de19c9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731773"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="6566d-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6566d-102">CLRRuntimeHost Coclass</span></span>

<span data-ttu-id="6566d-103">Предоставляет интерфейсы для управления выполнением кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="6566d-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6566d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6566d-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="6566d-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6566d-105">Interfaces</span></span>  
  
|<span data-ttu-id="6566d-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="6566d-106">Interface</span></span>|<span data-ttu-id="6566d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6566d-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="6566d-108">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6566d-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="6566d-109">Предоставляет методы для управления выполнением приложений средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="6566d-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="6566d-110">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="6566d-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="6566d-111">Предоставляет методы для проверки переносимых исполняемых образов и для подробных отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="6566d-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6566d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6566d-112">Requirements</span></span>  

 <span data-ttu-id="6566d-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6566d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6566d-114">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="6566d-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6566d-115">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6566d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6566d-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6566d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6566d-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6566d-117">See also</span></span>

- [<span data-ttu-id="6566d-118">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="6566d-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
