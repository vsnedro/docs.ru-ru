---
title: Интерфейс ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: a66012651d4b307d06a5a3bff675a248cc0ee376
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976360"
---
# <a name="icordebugdebugevent-interface"></a>Интерфейс ICorDebugDebugEvent
Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetEventKind](icordebugdebugevent-geteventkind-method.md)|Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.|  
|[Метод GetThread](icordebugdebugevent-getthread-method.md)|Получает поток, в котором произошло событие.|  
  
## <a name="remarks"></a>Remarks  
 Следующие интерфейсы являются производными от интерфейса `ICorDebugDebugEvent`.  
  
- [ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)  
  
- [ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)  
  
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
