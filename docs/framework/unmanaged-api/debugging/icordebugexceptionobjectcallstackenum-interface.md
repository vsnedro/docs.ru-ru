---
title: Интерфейс ICorDebugExceptionObjectCallStackEnum
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 1c45faecdb8b95af8d9e981962151c2c5d071a4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731895"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>Интерфейс ICorDebugExceptionObjectCallStackEnum

Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения. Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)|Возвращает указанное число объектов [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) , содержащих сведения о стеке вызовов объекта исключения.|  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugExceptionObjectCallStackEnum`Интерфейс реализует интерфейс ICorDebugEnum.  
  
 `ICorDebugExceptionObjectCallStackEnum`Экземпляр заполняется объектами [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) путем вызова метода [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . Элементы стека вызовов в коллекции можно перечислить, вызвав метод [ICorDebugExceptionObjectCallStackEnum:: Next.](icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
