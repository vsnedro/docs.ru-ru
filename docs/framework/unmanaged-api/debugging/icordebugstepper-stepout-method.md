---
description: 'Дополнительные сведения о методе ICorDebugStepper:: Steping.'
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
ms.openlocfilehash: ef404c928ab711aef8032655a02cbd917416e806
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717619"
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
  
 В платформа .NET Framework версии 2,0 не используйте `StepOut` с установленным флагом STOP_UNMANAGED, так как он завершится ошибкой. (Используйте [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) для установки флагов для пошагового выполнения.) Отладчики взаимодействия должны выполнять шаг с заходом в собственный код.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
