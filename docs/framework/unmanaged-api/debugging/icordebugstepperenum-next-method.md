---
title: Метод ICorDebugStepperEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
ms.openlocfilehash: b8156b858bde550bb66a8f4ac254f850058ea1a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697198"
---
# <a name="icordebugstepperenumnext-method"></a>Метод ICorDebugStepperEnum::Next

Возвращает указанное число экземпляров ICorDebugStepper из перечисления, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 окне Число `ICorDebugStepper` извлекаемых экземпляров.  
  
 `steppers`  
 заполняет Массив указателей, каждый из которых указывает на `ICorDebugStepper` объект.  
  
 `pceltFetched`  
 заполняет Указатель на число `ICorDebugStepper` фактически возвращенных экземпляров. Это значение может быть равно NULL `celt` , если равно единице.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
