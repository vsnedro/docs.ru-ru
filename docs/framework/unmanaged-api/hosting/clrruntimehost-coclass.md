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
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616808"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="b2265-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b2265-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="b2265-103">Предоставляет интерфейсы для управления выполнением кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2265-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2265-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2265-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b2265-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b2265-105">Interfaces</span></span>  
  
|<span data-ttu-id="b2265-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="b2265-106">Interface</span></span>|<span data-ttu-id="b2265-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b2265-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b2265-108">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b2265-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="b2265-109">Предоставляет методы для управления выполнением приложений средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2265-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="b2265-110">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="b2265-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="b2265-111">Предоставляет методы для проверки переносимых исполняемых образов и для подробных отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="b2265-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2265-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b2265-112">Requirements</span></span>  
 <span data-ttu-id="b2265-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2265-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2265-114">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="b2265-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b2265-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2265-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2265-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2265-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2265-117">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="b2265-117">See also</span></span>

- [<span data-ttu-id="b2265-118">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="b2265-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
