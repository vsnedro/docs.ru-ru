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
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677860"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="1bc97-102">Структура BucketParameters</span><span class="sxs-lookup"><span data-stu-id="1bc97-102">BucketParameters Structure</span></span>

<span data-ttu-id="1bc97-103">Хранит имя типа события и параметры для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="1bc97-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bc97-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="1bc97-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1bc97-105">Members</span></span>  
  
|<span data-ttu-id="1bc97-106">Член</span><span class="sxs-lookup"><span data-stu-id="1bc97-106">Member</span></span>|<span data-ttu-id="1bc97-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1bc97-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="1bc97-108">`true`значение, если оставшаяся часть этой структуры является допустимой. в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="1bc97-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="1bc97-109">Имя типа события.</span><span class="sxs-lookup"><span data-stu-id="1bc97-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="1bc97-110">Массив строк, каждый из которых задает параметр для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="1bc97-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1bc97-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1bc97-111">Requirements</span></span>  

 <span data-ttu-id="1bc97-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bc97-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bc97-113">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="1bc97-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1bc97-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bc97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc97-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1bc97-115">See also</span></span>

- [<span data-ttu-id="1bc97-116">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="1bc97-116">Hosting Structures</span></span>](hosting-structures.md)
