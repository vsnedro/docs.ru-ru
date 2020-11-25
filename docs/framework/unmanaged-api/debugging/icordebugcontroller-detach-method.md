---
title: Метод ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: 55acb6e3ec60925cba3d8aa5328547c54f270356
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732675"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="689b3-102">Метод ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="689b3-102">ICorDebugController::Detach Method</span></span>

<span data-ttu-id="689b3-103">Отсоединяет отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="689b3-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="689b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="689b3-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="689b3-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="689b3-105">Remarks</span></span>  

 <span data-ttu-id="689b3-106">Процесс или домен приложения продолжит выполнение в обычном режиме, но объект "ICorDebugProcess" или "ICorDebugAppDomain" больше не является допустимым, и последующие обратные вызовы выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="689b3-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="689b3-107">В .NET Framework версии 2,0, если включена отладка неуправляемого кода, этот метод завершится ошибкой из-за ограничений операционной системы.</span><span class="sxs-lookup"><span data-stu-id="689b3-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="689b3-108">Требования</span><span class="sxs-lookup"><span data-stu-id="689b3-108">Requirements</span></span>  

 <span data-ttu-id="689b3-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="689b3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="689b3-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="689b3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="689b3-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="689b3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="689b3-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="689b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689b3-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="689b3-113">See also</span></span>
