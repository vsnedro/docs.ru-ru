---
title: Перечисление CorManifestResourceFlags
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
ms.openlocfilehash: ebdff88e9fdf499b809d56c4c29a906dbef9ec40
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008980"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="86dc7-102">Перечисление CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="86dc7-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="86dc7-103">Указывает видимость ресурсов, закодированных в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="86dc7-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86dc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86dc7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="86dc7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="86dc7-105">Members</span></span>  
  
|<span data-ttu-id="86dc7-106">Член</span><span class="sxs-lookup"><span data-stu-id="86dc7-106">Member</span></span>|<span data-ttu-id="86dc7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="86dc7-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="86dc7-108">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="86dc7-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="86dc7-109">Ресурсы являются общедоступными.</span><span class="sxs-lookup"><span data-stu-id="86dc7-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="86dc7-110">Ресурсы являются частными.</span><span class="sxs-lookup"><span data-stu-id="86dc7-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86dc7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="86dc7-111">Requirements</span></span>  
 <span data-ttu-id="86dc7-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86dc7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86dc7-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="86dc7-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="86dc7-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86dc7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86dc7-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="86dc7-115">See also</span></span>

- [<span data-ttu-id="86dc7-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="86dc7-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
