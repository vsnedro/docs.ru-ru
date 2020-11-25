---
title: Интерфейс ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
ms.openlocfilehash: 5165ef081aad849c11747807d8cc76b2df0a6c74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729321"
---
# <a name="icordebugthread-interface"></a>Интерфейс ICorDebugThread

Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](icordebugthread-clearcurrentexception-method.md)|Этот метод не реализован. Не используйте его.|  
|[Метод CreateEval](icordebugthread-createeval-method.md)|Создает объект ICorDebugEval, который работает с этим объектом `ICorDebugThread` .|  
|[Метод CreateStepper](icordebugthread-createstepper-method.md)|Создает объект ICorDebugStepper, позволяющий пошаговое выполнение активного кадра в этом объекте `ICorDebugThread` .|  
|[Метод EnumerateChains](icordebugthread-enumeratechains-method.md)|Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в этом `ICorDebugThread` .|  
|[Метод GetActiveChain](icordebugthread-getactivechain-method.md)|Возвращает указатель интерфейса на активный ICorDebugChain для этого объекта `ICorDebugThread` .|  
|[Метод GetActiveFrame](icordebugthread-getactiveframe-method.md)|Получает указатель интерфейса на активный объект ICorDebugFrame для этого `ICorDebugThread` .|  
|[Метод GetAppDomain](icordebugthread-getappdomain-method.md)|Возвращает указатель интерфейса на домен приложения, в котором выполняется в `ICorDebugThread` данный момент.|  
|[Метод GetCurrentException](icordebugthread-getcurrentexception-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.|  
|[Метод GetDebugState](icordebugthread-getdebugstate-method.md)|Возвращает значение Кордебугсреадстате, описывающее текущее состояние отладки этого объекта `ICorDebugThread` .|  
|[Метод GetHandle](icordebugthread-gethandle-method.md)|Возвращает текущий обработчик для активной части этого объекта `ICorDebugThread` .|  
|[Метод GetID](icordebugthread-getid-method.md)|Возвращает идентификатор текущей операционной системы активной части `ICorDebugThread` .|  
|[Метод GetObject](icordebugthread-getobject-method.md)|Возвращает указатель интерфейса на поток среды CLR.|  
|[Метод GetProcess](icordebugthread-getprocess-method.md)|Возвращает указатель интерфейса для процесса, частью которого является эта `ICorDebugThread` форма.|  
|[Метод GetRegisterSet](icordebugthread-getregisterset-method.md)|Возвращает указатель интерфейса на набор регистров, связанный с этим `ICorDebugThread` .|  
|[Метод GetUserState](icordebugthread-getuserstate-method.md)|Возвращает побитовое сочетание значений Кордебугусерстате, описывающих текущее состояние этого объекта `ICorDebugThread` .|  
|[Метод SetDebugState](icordebugthread-setdebugstate-method.md)|Задает побитовое сочетание `CorDebugThreadState` значений, описывающих состояние отладки этого объекта `ICorDebugThread` .|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
