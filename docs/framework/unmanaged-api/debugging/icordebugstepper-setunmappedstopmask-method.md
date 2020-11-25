---
title: Метод ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: 50fad8b38a6b33d0ddbb2f0f20676296c3d66737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698764"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>Метод ICorDebugStepper::SetUnmappedStopMask

Задает значение, указывающее тип несопоставленного кода, в котором выполнение будет остановлено.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mask`  
 окне Значение перечисления Кордебугунмаппедстоп, указывающее тип несопоставленного кода, в котором отладчик остановит выполнение.  
  
 Значение по умолчанию — STOP_OTHER_UNMAPPED. Значение STOP_UNMANAGED допустимо только при отладке взаимодействия.  
  
## <a name="remarks"></a>Комментарии  

 Когда отладчик находит JIT-компиляцию, которая не имеет соответствующего сопоставления с MSIL, он прекращает выполнение, если установлен флаг, указывающий этот тип несопоставленного кода. в противном случае выполнение по шагам прозрачно продолжится.  
  
 Если отладчик не использует средство многошагового режима для входа в метод, он не обязательно будет выполнять шаг с обходом несопоставленного кода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
