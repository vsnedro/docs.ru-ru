---
title: Метод ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 39d2fd0163b0e61295187461d5dbdf5742450306
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379520"
---
# <a name="icordebugstepperstep-method"></a>Метод ICorDebugStepper::Step
Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток, и, при необходимости, для продолжения пошагового выполнения функций, которые вызываются в потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bStepIn`  
 окне Задайте для значение, чтобы `true` выполнить шаг с заходом в функцию, которая вызывается в потоке. Задайте для значение `false` , чтобы выполнить шаг с обходом функции.  
  
## <a name="remarks"></a>Remarks  
 Шаг завершается, когда среда CLR выполняет следующую управляемую инструкцию в кадре этого средства. Если `Step` метод вызывается в пошаговом процессе, который не находится в управляемом коде, шаг будет выполнен, когда поток выполняет следующую инструкцию управляемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
