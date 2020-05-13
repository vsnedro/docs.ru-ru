---
title: Метод ICorDebugObjectValue::IsValueClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
ms.openlocfilehash: 13b100012215a7c2cee51ad5af39ec1447ab4e5b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207510"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="df382-102">Метод ICorDebugObjectValue::IsValueClass</span><span class="sxs-lookup"><span data-stu-id="df382-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="df382-103">Возвращает значение, указывающее, является ли значение этого объекта типом значения.</span><span class="sxs-lookup"><span data-stu-id="df382-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df382-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df382-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df382-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df382-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="df382-106">заполняет Указатель на логическое значение, равное, `true` Если значение объекта, представленное этим "ICorDebugObjectValue", является типом значения, а не ссылочным типом; в противном случае `pbIsValueClass` — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="df382-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df382-107">Требования</span><span class="sxs-lookup"><span data-stu-id="df382-107">Requirements</span></span>  
 <span data-ttu-id="df382-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df382-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df382-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df382-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df382-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df382-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df382-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df382-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df382-112">См. также</span><span class="sxs-lookup"><span data-stu-id="df382-112">See also</span></span>
