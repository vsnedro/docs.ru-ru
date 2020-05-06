---
title: Перечисление CorDebugExceptionFlags
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 45de821dd52f7e153fc79ffde056ed959c654fce
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795954"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="1f7e8-102">Перечисление CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="1f7e8-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="1f7e8-103">Предоставляет дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="1f7e8-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f7e8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1f7e8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1f7e8-105">Members</span></span>  
  
|<span data-ttu-id="1f7e8-106">Участник</span><span class="sxs-lookup"><span data-stu-id="1f7e8-106">Member</span></span>|<span data-ttu-id="1f7e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1f7e8-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="1f7e8-108">Исключение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1f7e8-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="1f7e8-109">Исключение доступно для перехвата.</span><span class="sxs-lookup"><span data-stu-id="1f7e8-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="1f7e8-110">Время исключения все еще может быть таким, что отладчик не сможет его перехватить.</span><span class="sxs-lookup"><span data-stu-id="1f7e8-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="1f7e8-111">Например, если ниже текущего обратного вызова или события исключения, возникшего в результате JIT-вложения, нет никакого управляемого кода, такое исключение не может быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="1f7e8-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f7e8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f7e8-112">Remarks</span></span>  
 <span data-ttu-id="1f7e8-113">В более поздних версиях для этого перечисления могут быть добавлены новые значения, поэтому следует подготовить код, использующий `CorDebugExceptionFlags` для неожиданных значений.</span><span class="sxs-lookup"><span data-stu-id="1f7e8-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f7e8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f7e8-114">Requirements</span></span>  
 <span data-ttu-id="1f7e8-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f7e8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f7e8-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f7e8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f7e8-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f7e8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f7e8-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f7e8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7e8-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1f7e8-119">See also</span></span>

- [<span data-ttu-id="1f7e8-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="1f7e8-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
