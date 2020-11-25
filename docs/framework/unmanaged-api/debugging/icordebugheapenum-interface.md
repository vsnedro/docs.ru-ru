---
title: Интерфейс ICorDebugHeapEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: 312052fcd683acbccb9ca616992bd635490aa2a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724368"
---
# <a name="icordebugheapenum-interface"></a>Интерфейс ICorDebugHeapEnum

Предоставляет перечислитель для объектов в управляемой куче. Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](icordebugheapenum-next-method.md)|Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения об объектах в управляемой куче.|  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugHeapEnum`Интерфейс реализует интерфейс ICorDebugEnum.  
  
 `ICorDebugHeapEnum`Экземпляр заполняется [COR_HEAPOBJECT](cor-heapobject-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератехеап](icordebugprocess5-enumerateheap-method.md) . Каждый экземпляр [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции представляет собой либо динамический объект в куче, либо объект, который не является корневым для какого-либо объекта, но еще не был собран сборщиком мусора. Объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапенум:: Next](icordebugheapenum-next-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
