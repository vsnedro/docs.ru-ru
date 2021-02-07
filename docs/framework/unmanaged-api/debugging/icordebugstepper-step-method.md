---
description: 'Дополнительные сведения о методе ICorDebugStepper:: Step'
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
ms.openlocfilehash: cb45575f7818784addf67eacda35442764e706af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717632"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
