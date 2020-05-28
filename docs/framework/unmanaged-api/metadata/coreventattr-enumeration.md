---
title: Перечисление CorEventAttr
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007444"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="15576-102">Перечисление CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="15576-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="15576-103">Содержит значения, описывающие метаданные события.</span><span class="sxs-lookup"><span data-stu-id="15576-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15576-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15576-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="15576-105">Участники</span><span class="sxs-lookup"><span data-stu-id="15576-105">Members</span></span>  
  
|<span data-ttu-id="15576-106">Член</span><span class="sxs-lookup"><span data-stu-id="15576-106">Member</span></span>|<span data-ttu-id="15576-107">Описание</span><span class="sxs-lookup"><span data-stu-id="15576-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="15576-108">Указывает, что событие является специальным, и что его имя описывает, как это делать.</span><span class="sxs-lookup"><span data-stu-id="15576-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="15576-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="15576-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="15576-110">Указывает, что среда CLR должна проверять кодировку имени события.</span><span class="sxs-lookup"><span data-stu-id="15576-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15576-111">Требования</span><span class="sxs-lookup"><span data-stu-id="15576-111">Requirements</span></span>  
 <span data-ttu-id="15576-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15576-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15576-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="15576-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="15576-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15576-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15576-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="15576-115">See also</span></span>

- [<span data-ttu-id="15576-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="15576-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
