---
description: 'Дополнительные сведения о методе ICorDebugStepper:: Сетунмаппедстопмаск'
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
ms.openlocfilehash: 60b8fd4b74e1eeb76868fc6cdac308ff805e44db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717721"
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
  
## <a name="remarks"></a>Remarks  

 Когда отладчик находит JIT-компиляцию, которая не имеет соответствующего сопоставления с MSIL, он прекращает выполнение, если установлен флаг, указывающий этот тип несопоставленного кода. в противном случае выполнение по шагам прозрачно продолжится.  
  
 Если отладчик не использует средство многошагового режима для входа в метод, он не обязательно будет выполнять шаг с обходом несопоставленного кода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
