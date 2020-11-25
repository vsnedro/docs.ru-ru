---
title: Метод ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 06f403f0b653866428a41240f99833ec1180eb86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731086"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="43007-102">Метод ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="43007-102">ICorDebugValue::GetType Method</span></span>

<span data-ttu-id="43007-103">Возвращает тип примитива этого объекта "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="43007-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43007-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43007-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43007-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43007-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="43007-106">заполняет Указатель на значение перечисления "Корелементтипе", которое указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="43007-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43007-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="43007-107">Remarks</span></span>  

 <span data-ttu-id="43007-108">Если объект является сложным типом времени выполнения, этот тип можно исследовать с помощью соответствующих подклассов `ICorDebugValue` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="43007-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="43007-109">Например, "ICorDebugObjectValue", который наследует от `ICorDebugValue` , представляет сложный тип.</span><span class="sxs-lookup"><span data-stu-id="43007-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="43007-110">`GetType`Методы и [ICorDebugObjectValue:: coclass](icordebugobjectvalue-getclass-method.md) возвращают сведения о типе значения.</span><span class="sxs-lookup"><span data-stu-id="43007-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="43007-111">Они заменяются методом [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) , поддерживающим универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="43007-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43007-112">Требования</span><span class="sxs-lookup"><span data-stu-id="43007-112">Requirements</span></span>  

 <span data-ttu-id="43007-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43007-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43007-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43007-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43007-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43007-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43007-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43007-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43007-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43007-117">See also</span></span>
