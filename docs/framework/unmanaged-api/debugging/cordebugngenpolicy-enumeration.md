---
title: Перечисление CorDebugNGenPolicy
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: 036d3f12b38c19259fefaba674d0f9025a58d688
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795759"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ec588-102">Перечисление CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="ec588-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="ec588-103">Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="ec588-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec588-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec588-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ec588-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ec588-105">Members</span></span>  
  
|<span data-ttu-id="ec588-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="ec588-106">Member name</span></span>|<span data-ttu-id="ec588-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ec588-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ec588-108">В приложении для Магазина Windows 8. x использование образов из локального кэша образов в машинном кодах отключено.</span><span class="sxs-lookup"><span data-stu-id="ec588-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ec588-109">В классическом приложении этот параметр не действует.</span><span class="sxs-lookup"><span data-stu-id="ec588-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec588-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec588-110">Remarks</span></span>  
 <span data-ttu-id="ec588-111">`CorDebugNGENPolicy` Перечисление используется методом [метод ICorDebugProcess5:: EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ec588-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ec588-112">Отключение использования образов из локального кэша образов в машинном код обеспечивает единообразную отладку, гарантируя, что отладчик загружает отладочные скомпилированные КОМПИЛЯТОРом изображения вместо оптимизированных образов в машинном код.</span><span class="sxs-lookup"><span data-stu-id="ec588-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec588-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ec588-113">Requirements</span></span>  
 <span data-ttu-id="ec588-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec588-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec588-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec588-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec588-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec588-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec588-117">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec588-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec588-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec588-118">See also</span></span>

- [<span data-ttu-id="ec588-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="ec588-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
