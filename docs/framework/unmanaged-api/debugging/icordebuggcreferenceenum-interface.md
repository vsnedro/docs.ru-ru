---
description: 'Дополнительные сведения о: интерфейс ICorDebugGCReferenceEnum'
title: Интерфейс ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: ad4a61cdc2b30fb4c8e2be500eae878327c6b449
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801297"
---
# <a name="icordebuggcreferenceenum-interface"></a>Интерфейс ICorDebugGCReferenceEnum

Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Следующий метод](icordebuggcreferenceenum-next-method.md)|Возвращает указанное число экземпляров [COR_GC_REFERENCE](cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugGCReferenceEnum`Интерфейс реализует интерфейс "ICorDebugEnum".  
  
 `ICorDebugGCReferenceEnum`Экземпляр заполняется [COR_GC_REFERENCE](cor-gc-reference-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератегкреференцес](icordebugprocess5-enumerategcreferences-method.md) . [COR_GC_REFERENCE](cor-gc-reference-structure.md) объекты можно перечислить, вызвав метод [Икордебуггкреференце:: Next](icordebuggcreferenceenum-next-method.md) .  
  
 [COR_GC_REFERENCE](cor-gc-reference-structure.md) объекты в коллекции, заполненной этим методом, представляют три вида объектов:  
  
- Объекты из всех управляемых стеков. Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.  
  
- Объекты из таблицы Handle. Это включает в себя строгие ссылки ( `HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT` ) и статические переменные в модуле.  
  
- Объекты из очереди метода завершения. Очередь метода завершения помещает объекты в корни до запуска метода завершения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
