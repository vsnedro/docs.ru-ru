---
title: Метод ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 47c0c4dfa78e85bcc83f0bb2a333955c8e8666fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728372"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="6d914-102">Метод ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="6d914-102">ICorDebugValue::GetAddress Method</span></span>

<span data-ttu-id="6d914-103">Возвращает адрес этого объекта "ICorDebugValue", который находится в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="6d914-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d914-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d914-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d914-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d914-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="6d914-106">заполняет Указатель на `CORDB_ADDRESS` объект, указывающий адрес этого объекта значения.</span><span class="sxs-lookup"><span data-stu-id="6d914-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d914-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6d914-107">Remarks</span></span>  

 <span data-ttu-id="6d914-108">Если значение недоступно, возвращается 0 (нуль).</span><span class="sxs-lookup"><span data-stu-id="6d914-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="6d914-109">Это может произойти, если значение не меньше частично в регистрах или хранится в обработчике сборщика мусора ( `GCHandle` ).</span><span class="sxs-lookup"><span data-stu-id="6d914-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d914-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6d914-110">Requirements</span></span>  

 <span data-ttu-id="6d914-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d914-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d914-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d914-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d914-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d914-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d914-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d914-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d914-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6d914-115">See also</span></span>
