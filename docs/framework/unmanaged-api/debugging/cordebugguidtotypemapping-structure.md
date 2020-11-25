---
title: Структура CorDebugGuidToTypeMapping
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
ms.openlocfilehash: 859853521b741f42f1de7921de813941d2501173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729100"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="e1c55-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="e1c55-102">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="e1c55-103">Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="e1c55-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1c55-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e1c55-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e1c55-105">Members</span></span>  
  
|<span data-ttu-id="e1c55-106">Член</span><span class="sxs-lookup"><span data-stu-id="e1c55-106">Member</span></span>|<span data-ttu-id="e1c55-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e1c55-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="e1c55-108">Идентификатор GUID кэшированного типа среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c55-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="e1c55-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшированном типе.</span><span class="sxs-lookup"><span data-stu-id="e1c55-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1c55-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e1c55-110">Requirements</span></span>  

 <span data-ttu-id="e1c55-111">**Платформы:** среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c55-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="e1c55-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1c55-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1c55-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1c55-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1c55-114">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c55-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c55-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1c55-115">See also</span></span>

- [<span data-ttu-id="e1c55-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e1c55-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e1c55-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="e1c55-117">Debugging</span></span>](index.md)
