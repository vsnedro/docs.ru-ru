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
ms.openlocfilehash: 45ae947cda5b4ddadfb10f5b2bdc78a95f031703
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420696"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="fabd1-102">Структура StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="fabd1-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="fabd1-103">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="fabd1-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fabd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fabd1-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="fabd1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="fabd1-105">Members</span></span>  
  
|<span data-ttu-id="fabd1-106">Член</span><span class="sxs-lookup"><span data-stu-id="fabd1-106">Member</span></span>|<span data-ttu-id="fabd1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fabd1-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="fabd1-108">Указатель стека или ввод указателя стека (ESP) на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="fabd1-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="fabd1-109">Смещение кадра или регистр EBP на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="fabd1-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="fabd1-110">Указатель инструкции или ввод указателя инструкции (EIP) на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="fabd1-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fabd1-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fabd1-111">Remarks</span></span>  
 <span data-ttu-id="fabd1-112">Поскольку функции трассировки стека обычно должны возвращать только адрес, Смещение фрейма и адрес стека, при необходимости можно использовать `SimpleContext` структуру, а не большую `CONTEXT` структуру.</span><span class="sxs-lookup"><span data-stu-id="fabd1-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fabd1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fabd1-113">Requirements</span></span>  
 <span data-ttu-id="fabd1-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fabd1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fabd1-115">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="fabd1-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="fabd1-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fabd1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabd1-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fabd1-117">See also</span></span>

- [<span data-ttu-id="fabd1-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="fabd1-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="fabd1-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="fabd1-119">Debugging</span></span>](index.md)
