---
title: Интерфейс ICorDebugExceptionObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 8e4f745440936a39e22faf60d10a05a0bb110606
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975957"
---
# <a name="icordebugexceptionobjectvalue-interface"></a>Интерфейс ICorDebugExceptionObjectValue
Расширяет интерфейс "ICorDebugObjectValue" для предоставления сведений о трассировке стека из управляемого объекта исключения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|Возвращает перечислитель для стека вызовов, внедренного в объект исключения.|  
  
## <a name="remarks"></a>Remarks  
 Вызов метода `QueryInterface` будет выполнен для управляемых объектов, производных от <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
