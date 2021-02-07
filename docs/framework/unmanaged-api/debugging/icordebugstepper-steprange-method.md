---
description: 'Дополнительные сведения о методе ICorDebugStepper:: Степранже'
title: Метод ICorDebugStepper::StepRange
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: 868925ef301cca15b7887505e879f5fff02002e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717586"
---
# <a name="icordebugsteppersteprange-method"></a>Метод ICorDebugStepper::StepRange

Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток и возвращает, когда он достигает кода, находящегося за последним из указанных диапазонов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `bStepIn`  
 окне Задайте для значение, чтобы `true` выполнить шаг с заходом в функцию, которая вызывается в потоке. Задайте для значение `false` , чтобы выполнить шаг с обходом функции.  
  
 `ranges`  
 окне Массив структур COR_DEBUG_STEP_RANGE, каждый из которых задает диапазон.  
  
 `cRangeCount`  
 [in] Размер массива `ranges`.  
  
## <a name="remarks"></a>Remarks  

 `StepRange`Метод работает так же, как метод [ICorDebugStepper:: Step](icordebugstepper-step-method.md) , за исключением того, что он не завершается до достижения кода за пределами заданного диапазона.  
  
 Это может быть более эффективным, чем шаг с заходом по одной инструкции за раз. Диапазоны задаются в виде списка пар смещений от начала кадра средства Организации.  
  
 Диапазоны задаются относительно кода промежуточного языка MSIL метода. Вызовите [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) с, `false` чтобы сделать диапазоны относительно машинного кода метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
