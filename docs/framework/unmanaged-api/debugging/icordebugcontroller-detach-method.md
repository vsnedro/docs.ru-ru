---
description: 'Дополнительные сведения о методе: ICorDebugController::D етач'
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
ms.openlocfilehash: 763386fa72fab023becf4a360556e61d500c7949
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764671"
---
# <a name="icordebugcontrollerdetach-method"></a>Метод ICorDebugController::Detach

Отсоединяет отладчик от процесса или домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Remarks  

 Процесс или домен приложения продолжит выполнение в обычном режиме, но объект "ICorDebugProcess" или "ICorDebugAppDomain" больше не является допустимым, и последующие обратные вызовы выполняться не будут.  
  
 В платформа .NET Framework версии 2,0, если включена отладка неуправляемого кода, этот метод завершится ошибкой из-за ограничений операционной системы.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
