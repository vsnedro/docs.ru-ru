---
title: Перечисление CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: 772f1f0dee260ad3752b2f89e5fbe0d6bc27b87b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795655"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="a6302-102">Перечисление CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="a6302-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="a6302-103">Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.</span><span class="sxs-lookup"><span data-stu-id="a6302-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6302-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6302-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="a6302-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a6302-105">Members</span></span>  
  
|<span data-ttu-id="a6302-106">Участник</span><span class="sxs-lookup"><span data-stu-id="a6302-106">Member</span></span>|<span data-ttu-id="a6302-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a6302-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="a6302-108">Не останавливайте в любом типе несопоставленного кода.</span><span class="sxs-lookup"><span data-stu-id="a6302-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="a6302-109">Останавливает в коде пролога.</span><span class="sxs-lookup"><span data-stu-id="a6302-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="a6302-110">Прерывать в коде эпилога.</span><span class="sxs-lookup"><span data-stu-id="a6302-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="a6302-111">Прерывать в коде, не имеющем сведений о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="a6302-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="a6302-112">Прерывать в несопоставленном коде, который не помещается ни в прологе, ни в том, ни в какую информацию, ни в неуправляемой категории.</span><span class="sxs-lookup"><span data-stu-id="a6302-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="a6302-113">Останавливает в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="a6302-113">Stop in unmanaged code.</span></span> <span data-ttu-id="a6302-114">Это значение допустимо только при отладке взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="a6302-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="a6302-115">Останавливаются во всех типах несопоставленного кода.</span><span class="sxs-lookup"><span data-stu-id="a6302-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6302-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6302-116">Remarks</span></span>  
 <span data-ttu-id="a6302-117">Используйте метод [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) , чтобы задать флаги, указывающие Несопоставленный код, в котором будет останавливаться средство Организации.</span><span class="sxs-lookup"><span data-stu-id="a6302-117">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6302-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a6302-118">Requirements</span></span>  
 <span data-ttu-id="a6302-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6302-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6302-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6302-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6302-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6302-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6302-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6302-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6302-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6302-123">See also</span></span>

- [<span data-ttu-id="a6302-124">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="a6302-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
