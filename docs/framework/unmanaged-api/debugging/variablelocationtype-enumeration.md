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
ms.openlocfilehash: 455fd06dbdbfd5d9753f3d7270647a742751d804
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420660"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="f180f-102">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="f180f-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="f180f-103">Указывает тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="f180f-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f180f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f180f-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="f180f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f180f-105">Members</span></span>  
  
|<span data-ttu-id="f180f-106">Член</span><span class="sxs-lookup"><span data-stu-id="f180f-106">Member</span></span>|<span data-ttu-id="f180f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f180f-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="f180f-108">Переменная находится в регистре.</span><span class="sxs-lookup"><span data-stu-id="f180f-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="f180f-109">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="f180f-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="f180f-110">Переменная не хранится в регистре или расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="f180f-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f180f-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f180f-111">Remarks</span></span>  
 <span data-ttu-id="f180f-112">Член `VariableLocationType` перечисления возвращается методом [ICorDebugVariableHome:: жетлокатионтипе](icordebugvariablehome-getlocationtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f180f-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f180f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f180f-113">Requirements</span></span>  
 <span data-ttu-id="f180f-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f180f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f180f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f180f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f180f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f180f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f180f-117">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f180f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f180f-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f180f-118">See also</span></span>

- [<span data-ttu-id="f180f-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="f180f-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
