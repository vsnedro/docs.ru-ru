---
title: Перечисление CorDebugJITCompilerFlags
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
ms.openlocfilehash: 8be8ce36b557831bc0997dd1c69abb924390d051
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795829"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="421ba-102">Перечисление CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="421ba-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="421ba-103">Содержит значения, которые влияют на поведение управляемого JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="421ba-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="421ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="421ba-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="421ba-105">Участники</span><span class="sxs-lookup"><span data-stu-id="421ba-105">Members</span></span>  
  
|<span data-ttu-id="421ba-106">Участник</span><span class="sxs-lookup"><span data-stu-id="421ba-106">Member</span></span>|<span data-ttu-id="421ba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="421ba-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="421ba-108">Указывает, что компилятор должен отслеживанить данные компиляции и допускает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="421ba-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="421ba-109">Указывает, что компилятор должен отслеживаниь данных компиляции, но отключает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="421ba-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="421ba-110">Указывает, что компилятор должен выполнять трассировку данных компиляции, отключать оптимизации и включать технологии "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="421ba-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="421ba-111">Требования</span><span class="sxs-lookup"><span data-stu-id="421ba-111">Requirements</span></span>  
 <span data-ttu-id="421ba-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421ba-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421ba-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="421ba-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="421ba-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="421ba-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="421ba-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421ba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421ba-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="421ba-116">See also</span></span>

- [<span data-ttu-id="421ba-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="421ba-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
