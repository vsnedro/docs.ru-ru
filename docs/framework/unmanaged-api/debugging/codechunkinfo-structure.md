---
title: Структура CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727436"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="60d22-102">Структура CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="60d22-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="60d22-103">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="60d22-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60d22-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="60d22-105">Члены</span><span class="sxs-lookup"><span data-stu-id="60d22-105">Members</span></span>  
  
|<span data-ttu-id="60d22-106">Член</span><span class="sxs-lookup"><span data-stu-id="60d22-106">Member</span></span>|<span data-ttu-id="60d22-107">Описание</span><span class="sxs-lookup"><span data-stu-id="60d22-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="60d22-108">`CORDB_ADDRESS`Значение, указывающее начальный адрес фрагмента.</span><span class="sxs-lookup"><span data-stu-id="60d22-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="60d22-109">Размер блока в байтах.</span><span class="sxs-lookup"><span data-stu-id="60d22-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60d22-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="60d22-110">Remarks</span></span>  

 <span data-ttu-id="60d22-111">Единственный фрагмент кода — это область машинного кода, которая является частью объекта кода, например функции.</span><span class="sxs-lookup"><span data-stu-id="60d22-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d22-112">Требования</span><span class="sxs-lookup"><span data-stu-id="60d22-112">Requirements</span></span>  

 <span data-ttu-id="60d22-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60d22-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60d22-114">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="60d22-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="60d22-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60d22-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60d22-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60d22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d22-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="60d22-117">See also</span></span>

- [<span data-ttu-id="60d22-118">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="60d22-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="60d22-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="60d22-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="60d22-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="60d22-120">Debugging</span></span>](index.md)
