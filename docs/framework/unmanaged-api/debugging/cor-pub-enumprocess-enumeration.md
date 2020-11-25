---
title: Перечисление COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
ms.openlocfilehash: 30a522fbf96aebaa96f33f4a1dc381683f183871
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726422"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="3f8be-102">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="3f8be-102">COR_PUB_ENUMPROCESS Enumeration</span></span>

<span data-ttu-id="3f8be-103">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="3f8be-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f8be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f8be-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="3f8be-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3f8be-105">Members</span></span>  
  
|<span data-ttu-id="3f8be-106">Имя участника</span><span class="sxs-lookup"><span data-stu-id="3f8be-106">Member name</span></span>|<span data-ttu-id="3f8be-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3f8be-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="3f8be-108">Управляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="3f8be-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f8be-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3f8be-109">Remarks</span></span>  

 <span data-ttu-id="3f8be-110">Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.</span><span class="sxs-lookup"><span data-stu-id="3f8be-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f8be-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3f8be-111">Requirements</span></span>  

 <span data-ttu-id="3f8be-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f8be-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f8be-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="3f8be-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3f8be-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f8be-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f8be-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f8be-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8be-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f8be-116">See also</span></span>

- [<span data-ttu-id="3f8be-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="3f8be-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
