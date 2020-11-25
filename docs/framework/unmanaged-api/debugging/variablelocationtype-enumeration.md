---
title: Перечисление VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725265"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="0b10a-102">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="0b10a-102">VariableLocationType Enumeration</span></span>

<span data-ttu-id="0b10a-103">Указывает тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="0b10a-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b10a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b10a-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="0b10a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0b10a-105">Members</span></span>  
  
|<span data-ttu-id="0b10a-106">Член</span><span class="sxs-lookup"><span data-stu-id="0b10a-106">Member</span></span>|<span data-ttu-id="0b10a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0b10a-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="0b10a-108">Переменная находится в регистре.</span><span class="sxs-lookup"><span data-stu-id="0b10a-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="0b10a-109">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="0b10a-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="0b10a-110">Переменная не хранится в регистре или расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="0b10a-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b10a-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0b10a-111">Remarks</span></span>  

 <span data-ttu-id="0b10a-112">Член `VariableLocationType` перечисления возвращается методом [ICorDebugVariableHome:: жетлокатионтипе](icordebugvariablehome-getlocationtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0b10a-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b10a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0b10a-113">Requirements</span></span>  

 <span data-ttu-id="0b10a-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b10a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b10a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b10a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b10a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b10a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b10a-117">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b10a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b10a-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b10a-118">See also</span></span>

- [<span data-ttu-id="0b10a-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0b10a-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
