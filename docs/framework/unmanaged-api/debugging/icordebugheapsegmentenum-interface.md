---
description: 'Дополнительные сведения о: интерфейс Икордебугхеапсегментенум'
title: Интерфейс ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: 614bae0ea5e3eb7816fdeec23a0dc7aa6e44801d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660886"
---
# <a name="icordebugheapsegmentenum-interface"></a>Интерфейс ICorDebugHeapSegmentEnum

Предоставляет перечислитель для областей памяти управляемой кучи. Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Следующий метод](icordebugheapsegmentenum-next-method.md)|Возвращает указанное число экземпляров [COR_SEGMENT](cor-segment-structure.md) , содержащих сведения о регионах управляемой кучи.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugHeapSegmentEnum`Интерфейс реализует интерфейс ICorDebugEnum.  
  
 `ICorDebugHeapSegmentEnum`Экземпляр заполняется [COR_SEGMENT](cor-segment-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератехеапрегионс](icordebugprocess5-enumerateheapregions-method.md) . Объекты [COR_SEGMENT](cor-segment-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапсегментенум:: Next](icordebugheapsegmentenum-next-method.md) .  
  
 `ICorDebugHeapSegmentEnum`Объект Collection перечисляет все области памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах. Он может включать сведения о пустых или зарезервированных регионах памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
