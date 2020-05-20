---
title: Структура BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 7037065be138c369b847e7f86de7b46fc5ae601a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616883"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="5eb9b-102">Структура BucketParameters</span><span class="sxs-lookup"><span data-stu-id="5eb9b-102">BucketParameters Structure</span></span>
<span data-ttu-id="5eb9b-103">Хранит имя типа события и параметры для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="5eb9b-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5eb9b-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="5eb9b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5eb9b-105">Members</span></span>  
  
|<span data-ttu-id="5eb9b-106">Член</span><span class="sxs-lookup"><span data-stu-id="5eb9b-106">Member</span></span>|<span data-ttu-id="5eb9b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5eb9b-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="5eb9b-108">`true`значение, если оставшаяся часть этой структуры является допустимой. в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="5eb9b-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="5eb9b-109">Имя типа события.</span><span class="sxs-lookup"><span data-stu-id="5eb9b-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="5eb9b-110">Массив строк, каждый из которых задает параметр для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="5eb9b-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5eb9b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5eb9b-111">Requirements</span></span>  
 <span data-ttu-id="5eb9b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eb9b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb9b-113">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="5eb9b-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5eb9b-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eb9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb9b-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5eb9b-115">See also</span></span>

- [<span data-ttu-id="5eb9b-116">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="5eb9b-116">Hosting Structures</span></span>](hosting-structures.md)
