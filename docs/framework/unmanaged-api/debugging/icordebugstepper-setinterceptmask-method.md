---
title: Метод ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: aaba751a58e5b23b98b1d0629ea3cc9e1e7a83a9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379004"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>Метод ICorDebugStepper::SetInterceptMask
Задает значение, указывающее типы кода, в который выполняется пошаговое выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mask`  
 окне Сочетание значений перечисления CorDebugIntercept, определяющих типы кода.  
  
## <a name="remarks"></a>Remarks  
 Если задан бит для перехватчика, средство пошагового выполнения будет выполнено при обнаружении заданного типа перехвата кода. Если бит сброшен, перехват кода будет пропущен.  
  
 `SetInterceptMask`Метод может иметь непредвиденные взаимодействия с [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) (от точки зрения пользователя). Например, если единственная видимая (т. е. не внутренняя) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO не задана (см. метод [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) и перечисление кордебугунмаппедстоп), средство организации пошаговое руководство будет пройдет инициализацию класса. По умолчанию будет использоваться только значение INTERCEPT_NONE `CorDebugIntercept` перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
