---
title: 'Метод ICorDebugVariableHome::'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 7f912f4b13620b567f5aa097604e98112d85f02d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711758"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="2841a-102">Метод ICorDebugVariableHome::</span><span class="sxs-lookup"><span data-stu-id="2841a-102">ICorDebugVariableHome::GetRegister Method</span></span>

<span data-ttu-id="2841a-103">Возвращает регистр, содержащий переменную с типом расположения `VLT_REGISTER` , и базовый регистр для переменной с типом расположения `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="2841a-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2841a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2841a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2841a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2841a-105">Parameters</span></span>  

 `pRegister`  
 <span data-ttu-id="2841a-106">заполняет Значение перечисления CorDebugRegister, указывающее регистр для переменной с типом расположения `VLT_REGISTER` и базовый регистр для переменной с типом расположения `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="2841a-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2841a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2841a-107">Return Value</span></span>  

 <span data-ttu-id="2841a-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2841a-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="2841a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="2841a-109">Value</span></span>|<span data-ttu-id="2841a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2841a-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2841a-111">Переменная находится в регистре, указанном `pRegister` аргументом.</span><span class="sxs-lookup"><span data-stu-id="2841a-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2841a-112">Переменная не находится в регистре или расположении, относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="2841a-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2841a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2841a-113">Requirements</span></span>  

 <span data-ttu-id="2841a-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2841a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2841a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2841a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2841a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2841a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2841a-117">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2841a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2841a-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2841a-118">See also</span></span>

- [<span data-ttu-id="2841a-119">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="2841a-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="2841a-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="2841a-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
