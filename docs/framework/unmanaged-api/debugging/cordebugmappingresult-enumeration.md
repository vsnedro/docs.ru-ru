---
title: Перечисление CorDebugMappingResult
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: 0e7afa386af1bd2eebc2b58592d01b764660248f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704699"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="f4b1f-102">Перечисление CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="f4b1f-102">CorDebugMappingResult Enumeration</span></span>

<span data-ttu-id="f4b1f-103">Предоставляет сведения о том, как было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4b1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4b1f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="f4b1f-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f4b1f-105">Members</span></span>  
  
|<span data-ttu-id="f4b1f-106">Член</span><span class="sxs-lookup"><span data-stu-id="f4b1f-106">Member</span></span>|<span data-ttu-id="f4b1f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f4b1f-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="f4b1f-108">Машинный код находится в прологе, поэтому значение IP-адреса равно 0.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="f4b1f-109">Машинный код находится в заключительном фрагменте, поэтому значение IP-адреса является адресом последней инструкции метода.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="f4b1f-110">Для метода нет доступных сведений о сопоставлении, поэтому значение IP-адреса равно 0.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="f4b1f-111">Хотя для метода есть сведения о сопоставлении, текущий адрес не может быть сопоставлен с кодом на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="f4b1f-112">Значение IP-адреса равно 0.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="f4b1f-113">Либо метод полностью сопоставлен с кодом MSIL, либо кадр был интерпретирован, поэтому значение IP-адреса является точным.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="f4b1f-114">Метод успешно сопоставлен, но значение IP-адреса может быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4b1f-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f4b1f-115">Remarks</span></span>  

 <span data-ttu-id="f4b1f-116">Для получения значения указателя инструкции можно использовать метод [ICorDebugILFrame:: GetIP](icordebugilframe-getip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f4b1f-116">You can use the [ICorDebugILFrame::GetIP](icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4b1f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f4b1f-117">Requirements</span></span>  

 <span data-ttu-id="f4b1f-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4b1f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4b1f-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4b1f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4b1f-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4b1f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4b1f-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4b1f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b1f-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f4b1f-122">See also</span></span>

- [<span data-ttu-id="f4b1f-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="f4b1f-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
