---
title: Интерфейс ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695820"
---
# <a name="icordebugmoduledebugevent-interface"></a>Интерфейс ICorDebugModuleDebugEvent

Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetModule](icordebugmoduledebugevent-getmodule-method.md)|Возвращает объединенный модуль, который только что был загружен или выгружен.|  
  
## <a name="remarks"></a>Комментарии  

 Типы событий [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) реализуют этот интерфейс.  
  
> [!NOTE]
> Этот интерфейс доступен только в машинном коде .NET. Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
