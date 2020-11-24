---
title: Структура StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 30775b4a6f904d06b9c77e6b2b64aec693c446d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671802"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="4c8a5-102">Структура StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="4c8a5-102">StackTrace_SimpleContext Structure</span></span>

<span data-ttu-id="4c8a5-103">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="4c8a5-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c8a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c8a5-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="4c8a5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4c8a5-105">Members</span></span>  
  
|<span data-ttu-id="4c8a5-106">Член</span><span class="sxs-lookup"><span data-stu-id="4c8a5-106">Member</span></span>|<span data-ttu-id="4c8a5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4c8a5-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="4c8a5-108">Указатель стека или ввод указателя стека (ESP) на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="4c8a5-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="4c8a5-109">Смещение кадра или регистр EBP на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="4c8a5-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="4c8a5-110">Указатель инструкции или ввод указателя инструкции (EIP) на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="4c8a5-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c8a5-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4c8a5-111">Remarks</span></span>  

 <span data-ttu-id="4c8a5-112">Поскольку функции трассировки стека обычно должны возвращать только адрес, Смещение фрейма и адрес стека, при необходимости можно использовать `SimpleContext` структуру, а не большую `CONTEXT` структуру.</span><span class="sxs-lookup"><span data-stu-id="4c8a5-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c8a5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4c8a5-113">Requirements</span></span>  

 <span data-ttu-id="4c8a5-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c8a5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c8a5-115">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="4c8a5-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="4c8a5-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c8a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c8a5-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c8a5-117">See also</span></span>

- [<span data-ttu-id="4c8a5-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="4c8a5-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4c8a5-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="4c8a5-119">Debugging</span></span>](index.md)
