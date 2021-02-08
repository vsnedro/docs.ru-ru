---
description: 'Дополнительные сведения о: интерфейс ICorProfilerCallback5'
title: Интерфейс ICorProfilerCallback5
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: b80b27dc994ad556381228370ece92935d89d293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788661"
---
# <a name="icorprofilercallback5-interface"></a>Интерфейс ICorProfilerCallback5

Дополняет сведения, чтобы помочь профилировщику определить полное закрытие динамических объектов при использовании метода [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) или [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) вместе с методами [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) и [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .  
  
 Для подписки на уведомления, связанные с зависимыми дескрипторами профилировщик управляемой памяти должен реализовать `ICorProfilerCallback5`.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
