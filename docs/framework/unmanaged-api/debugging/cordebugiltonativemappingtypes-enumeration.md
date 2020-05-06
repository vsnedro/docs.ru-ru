---
title: Перечисление CorDebugIlToNativeMappingTypes
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: 808fc70a308eff1b05aa49ea2bb89fe53377c973
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795850"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="efa1a-102">Перечисление CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="efa1a-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="efa1a-103">Указывает, соответствует ли определенный диапазон машинных инструкций, представленный экземпляром структуры COR_DEBUG_IL_TO_NATIVE_MAP, Специальному региону кода.</span><span class="sxs-lookup"><span data-stu-id="efa1a-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efa1a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="efa1a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="efa1a-105">Members</span></span>  
  
|<span data-ttu-id="efa1a-106">Участник</span><span class="sxs-lookup"><span data-stu-id="efa1a-106">Member</span></span>|<span data-ttu-id="efa1a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="efa1a-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="efa1a-108">Диапазон машинных инструкций не соответствует ни одной специальной области кода.</span><span class="sxs-lookup"><span data-stu-id="efa1a-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="efa1a-109">Диапазон машинных инструкций соответствует прологу.</span><span class="sxs-lookup"><span data-stu-id="efa1a-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="efa1a-110">Диапазон машинных инструкций соответствует заключительному фрагменту.</span><span class="sxs-lookup"><span data-stu-id="efa1a-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efa1a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="efa1a-111">Requirements</span></span>  
 <span data-ttu-id="efa1a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa1a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa1a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efa1a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efa1a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa1a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efa1a-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa1a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="efa1a-116">See also</span></span>

- [<span data-ttu-id="efa1a-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="efa1a-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="efa1a-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="efa1a-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
