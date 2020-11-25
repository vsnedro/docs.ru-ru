---
title: Метод ICorDebugStepper::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 0a57dfe5bb4dfdc08a5e3f2238da6794e62bd958
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718284"
---
# <a name="icordebugstepperisactive-method"></a>Метод ICorDebugStepper::IsActive

Возвращает значение, указывающее, выполняется ли в данный момент шаг.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbActive`  
 заполняет Возвращает `true` , если средство Организации в данный момент исполняет шаг; в противном случае возвращает `false` .  
  
## <a name="remarks"></a>Комментарии  

 Любое действие шага остается активным до тех пор, пока отладчик не получит вызов [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) , который автоматически деактивирует средство Организации. Пошаговое руководство также может быть деактивировано преждевременно путем вызова [ICorDebugStepper::D еактивате](icordebugstepper-deactivate-method.md) до достижения условия обратного вызова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
