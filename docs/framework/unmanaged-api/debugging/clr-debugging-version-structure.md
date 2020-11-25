---
title: Структура CLR_DEBUGGING_VERSION
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 8a2abe847728a2bb1f1345ef73e55b58e4704001
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729815"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="0dd05-102">Структура CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="0dd05-102">CLR_DEBUGGING_VERSION Structure</span></span>

<span data-ttu-id="0dd05-103">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="0dd05-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dd05-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="0dd05-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0dd05-105">Members</span></span>  
  
|<span data-ttu-id="0dd05-106">Член</span><span class="sxs-lookup"><span data-stu-id="0dd05-106">Member</span></span>|<span data-ttu-id="0dd05-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0dd05-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="0dd05-108">Номер версии структуры</span><span class="sxs-lookup"><span data-stu-id="0dd05-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="0dd05-109">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="0dd05-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="0dd05-110">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="0dd05-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="0dd05-111">Номер построения.</span><span class="sxs-lookup"><span data-stu-id="0dd05-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="0dd05-112">Номер редакции сборки.</span><span class="sxs-lookup"><span data-stu-id="0dd05-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0dd05-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0dd05-113">Remarks</span></span>  

 <span data-ttu-id="0dd05-114">Структура аналогична `CLR_DEBUGGING_VERSION` структуре COR_VERSION, однако `CLR_DEBUGGING_VERSION` Структура предоставляет дополнительное поле версии структуры ( `wStructVersion` ).</span><span class="sxs-lookup"><span data-stu-id="0dd05-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="0dd05-115">В настоящее время для этого поля необходимо задать значение 0.</span><span class="sxs-lookup"><span data-stu-id="0dd05-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dd05-116">Требования</span><span class="sxs-lookup"><span data-stu-id="0dd05-116">Requirements</span></span>  

 <span data-ttu-id="0dd05-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dd05-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd05-118">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="0dd05-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0dd05-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dd05-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dd05-120">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dd05-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd05-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0dd05-121">See also</span></span>

- [<span data-ttu-id="0dd05-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="0dd05-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0dd05-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="0dd05-123">Debugging</span></span>](index.md)
