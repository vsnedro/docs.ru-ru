---
title: Метод ICorDebugValueBreakpoint::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
ms.openlocfilehash: 8b0ab22d4a782bb21e09d29c9121ef83782a4571
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722327"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="e8266-102">Метод ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="e8266-102">ICorDebugValueBreakpoint::GetValue Method</span></span>

<span data-ttu-id="e8266-103">Возвращает указатель интерфейса на объект "ICorDebugValue", представляющий значение объекта, для которого задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="e8266-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8266-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8266-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8266-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8266-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="e8266-106">заполняет Указатель на адрес `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="e8266-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8266-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e8266-107">Requirements</span></span>  

 <span data-ttu-id="e8266-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8266-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8266-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8266-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8266-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8266-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8266-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8266-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8266-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8266-112">See also</span></span>
