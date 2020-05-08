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
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975996"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>Интерфейс ICorDebugExceptionObjectCallStackEnum
Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения. Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)|Возвращает указанное число объектов [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) , содержащих сведения о стеке вызовов объекта исключения.|  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugExceptionObjectCallStackEnum` Интерфейс реализует интерфейс ICorDebugEnum.  
  
 `ICorDebugExceptionObjectCallStackEnum` Экземпляр заполняется объектами [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) путем вызова метода [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . Элементы стека вызовов в коллекции можно перечислить, вызвав метод [ICorDebugExceptionObjectCallStackEnum:: Next.](icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
