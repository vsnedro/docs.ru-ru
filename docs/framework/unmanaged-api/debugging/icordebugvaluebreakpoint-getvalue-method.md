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
ms.openlocfilehash: cc4e1a236f429894fe7ec304b9ccfd3bf717c188
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397012"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="2ad2c-102">Метод ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="2ad2c-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="2ad2c-103">Возвращает указатель интерфейса на объект "ICorDebugValue", представляющий значение объекта, для которого задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="2ad2c-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad2c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ad2c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ad2c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ad2c-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="2ad2c-106">заполняет Указатель на адрес `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="2ad2c-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad2c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2ad2c-107">Requirements</span></span>  
 <span data-ttu-id="2ad2c-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad2c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad2c-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ad2c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ad2c-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ad2c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ad2c-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad2c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad2c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2ad2c-112">See also</span></span>
