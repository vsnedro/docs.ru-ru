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
ms.openlocfilehash: 480fec4897dac73594515ba8bc0f0e96ceb79ace
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892917"
---
# <a name="icordebugcontrollerdetach-method"></a>Метод ICorDebugController::Detach
Отсоединяет отладчик от процесса или домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Remarks  
 Процесс или домен приложения продолжит выполнение в обычном режиме, но объект "ICorDebugProcess" или "ICorDebugAppDomain" больше не является допустимым, и последующие обратные вызовы выполняться не будут.  
  
 В .NET Framework версии 2,0, если включена отладка неуправляемого кода, этот метод завершится ошибкой из-за ограничений операционной системы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
