---
title: Перечисление CorDebugGenerationTypes
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 0443f58b79e60111756308cc4843daf86d1fc823
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795872"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="fc8a4-102">Перечисление CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="fc8a4-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="fc8a4-103">Указывает на создание области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="fc8a4-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc8a4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="fc8a4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="fc8a4-105">Members</span></span>  
  
|<span data-ttu-id="fc8a4-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="fc8a4-106">Member name</span></span>|<span data-ttu-id="fc8a4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fc8a4-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="fc8a4-108">Поколение 0.</span><span class="sxs-lookup"><span data-stu-id="fc8a4-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="fc8a4-109">Поколение 1.</span><span class="sxs-lookup"><span data-stu-id="fc8a4-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="fc8a4-110">Поколение 2.</span><span class="sxs-lookup"><span data-stu-id="fc8a4-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="fc8a4-111">Куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="fc8a4-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc8a4-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc8a4-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc8a4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fc8a4-113">Requirements</span></span>  
 <span data-ttu-id="fc8a4-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc8a4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc8a4-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc8a4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc8a4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc8a4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc8a4-117">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc8a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8a4-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fc8a4-118">See also</span></span>

- [<span data-ttu-id="fc8a4-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="fc8a4-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
