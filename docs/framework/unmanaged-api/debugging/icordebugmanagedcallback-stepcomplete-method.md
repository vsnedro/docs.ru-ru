---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: StepComplete'
title: Метод ICorDebugManagedCallback::StepComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
ms.openlocfilehash: 653abee26f09ac8877be9fa4183763739845666a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660366"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a>Метод ICorDebugManagedCallback::StepComplete

Уведомляет отладчик о завершении шага.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором выполнен шаг.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, в котором выполнен шаг.  
  
 `pStepper`  
 окне Указатель на объект ICorDebugStepper, представляющий шаг при выполнении кода.  
  
 `reason`  
 окне Значение перечисления Кордебугстепреасон, указывающее результат отдельного шага.  
  
## <a name="remarks"></a>Remarks  

 Средство организации пошагового режима можно использовать для продолжения пошагового выполнения, если отладка не будет завершена.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
