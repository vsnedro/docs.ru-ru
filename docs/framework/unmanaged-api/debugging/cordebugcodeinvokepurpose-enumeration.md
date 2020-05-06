---
title: Перечисление CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: 2e59d02093b9c2e2bda72c45de25975cbbdb7a29
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796019"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="481ba-102">Перечисление CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="481ba-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="481ba-103">Описывает, почему экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="481ba-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="481ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="481ba-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="481ba-105">Участники</span><span class="sxs-lookup"><span data-stu-id="481ba-105">Members</span></span>  
  
|<span data-ttu-id="481ba-106">Участник</span><span class="sxs-lookup"><span data-stu-id="481ba-106">Member</span></span>|<span data-ttu-id="481ba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="481ba-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="481ba-108">Отсутствует или неизвестно.</span><span class="sxs-lookup"><span data-stu-id="481ba-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="481ba-109">Управляемый код будет выполнять любую управляемую точку входа, например, обратный p-invoke.</span><span class="sxs-lookup"><span data-stu-id="481ba-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="481ba-110">Любые дополнительные цели неизвестны среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="481ba-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="481ba-111">Управляемый код будет выполнять статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="481ba-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="481ba-112">Управляемый код будет выполнять реализацию некоторого метода интерфейса, который был вызван.</span><span class="sxs-lookup"><span data-stu-id="481ba-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="481ba-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="481ba-113">Remarks</span></span>  
 <span data-ttu-id="481ba-114">Это перечисление используется методом [ICorDebugProcess6:: жетекспортстепинфо](icordebugprocess6-getexportstepinfo-method.md) для предоставления сведений о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="481ba-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="481ba-115">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="481ba-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="481ba-116">Требования</span><span class="sxs-lookup"><span data-stu-id="481ba-116">Requirements</span></span>  
 <span data-ttu-id="481ba-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="481ba-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="481ba-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="481ba-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="481ba-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="481ba-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="481ba-120">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="481ba-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481ba-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="481ba-121">See also</span></span>

- [<span data-ttu-id="481ba-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="481ba-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="481ba-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="481ba-123">Debugging</span></span>](index.md)
