---
title: Перечисление CLSID_RESOLUTION_FLAGS
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 5ac015f958d9504bbd14a66ead86548b8df32764
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616779"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="dfc7d-102">Перечисление CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="dfc7d-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="dfc7d-103">Содержит значения, которые указывают, как общеязыковая среда выполнения (CLR) должна разрешать `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="dfc7d-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfc7d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="dfc7d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dfc7d-105">Members</span></span>  
  
|<span data-ttu-id="dfc7d-106">Член</span><span class="sxs-lookup"><span data-stu-id="dfc7d-106">Member</span></span>|<span data-ttu-id="dfc7d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dfc7d-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="dfc7d-108">Указывает поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfc7d-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="dfc7d-109">Указывает, что среда выполнения выполняет поиск в реестре и применяет политику оболочки совместимости.</span><span class="sxs-lookup"><span data-stu-id="dfc7d-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfc7d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dfc7d-110">Requirements</span></span>  
 <span data-ttu-id="dfc7d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfc7d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfc7d-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dfc7d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dfc7d-113">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc7d-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="dfc7d-114">See also</span></span>

- [<span data-ttu-id="dfc7d-115">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="dfc7d-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
