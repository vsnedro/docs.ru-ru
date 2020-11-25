---
title: Метод ICorDebugStepper::StepOut
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 1396e7a8ca61734a9363a9c852502290675249d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727670"
---
# <a name="icordebugstepperstepout-method"></a>Метод ICorDebugStepper::StepOut

Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток и завершается, когда текущий кадр возвращает управление вызывающему кадру.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Remarks  

 `StepOut`Операция будет завершена после возврата в обычном режиме из текущего кадра в вызывающий кадр.  
  
 Если `StepOut` вызывается в неуправляемом коде, этот шаг завершается, когда текущий кадр возвращается в управляемый код, вызвавший его.  
  
 В .NET Framework версии 2,0 не используйте `StepOut` с установленным флагом STOP_UNMANAGED, так как он завершится ошибкой. (Используйте [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) для установки флагов для пошагового выполнения.) Отладчики взаимодействия должны выполнять шаг с заходом в собственный код.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
