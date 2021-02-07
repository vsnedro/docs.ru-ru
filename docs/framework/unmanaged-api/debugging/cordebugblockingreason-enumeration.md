---
description: Дополнительные сведения о перечислении Кордебугблоккингреасон
title: Перечисление CorDebugBlockingReason
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: c2d9c805549d046fe40ab5ea00f30e2fd0a680a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747114"
---
# <a name="cordebugblockingreason-enumeration"></a>Перечисление CorDebugBlockingReason

Указывает возможные причины блокировки потока на данном объекте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`BLOCKING_NONE`|Только для внутреннего использования.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Поток пытается получить критическую секцию, связанную с блокировкой монитора для объекта. Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> методов или.|  
|`BLOCKING_MONITOR_EVENT`|Поток ожидает события, связанного с блокировкой монитора для объекта. Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` методов.|  
  
## <a name="remarks"></a>Remarks  

 Если `BLOCKING_MONITOR_CRITICAL_SECTION` элемент или `BLOCKING_MONITOR_EVENT` используется в структуре [CorDebugBlockingObject](cordebugblockingobject-structure.md) , `pBlockingObject` элемент структуры указывает на интерфейс "ICorDebugValue", представляющий объект, который необходимо указать. Также гарантируется реализация интерфейса [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
