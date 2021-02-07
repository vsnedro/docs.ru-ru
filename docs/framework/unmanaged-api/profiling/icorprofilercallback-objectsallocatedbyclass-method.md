---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: Обжектсаллокатедбикласс'
title: Метод ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: df9f3dde27664de7db4afb264b221f640753ddb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745064"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>Метод ICorProfilerCallback::ObjectsAllocatedByClass

Уведомляет профилировщик о количестве экземпляров каждого указанного класса, созданных с момента последнего сбора мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>Параметры  

 `cClassCount`  
 окне Размер `classIds` `cObjects` массивов и.  
  
 `classIds`  
 окне Массив идентификаторов классов, где каждый идентификатор указывает класс с одним или несколькими экземплярами.  
  
 `cObjects`  
 окне Массив целых чисел, где каждое целое число указывает количество экземпляров для соответствующего класса в `classIds` массиве.  
  
## <a name="remarks"></a>Remarks  

 `classIds` `cObjects` Массивы и являются параллельными массивами. Например, `classIds[i]` и `cObjects[i]` сослаться на один и тот же класс. Если с момента предыдущего сбора мусора экземпляр класса не был создан, класс опускается. `ObjectsAllocatedByClass`Обратный вызов не будет сообщать объекты, выделенные в куче больших объектов.  
  
 Числа, сообщаемые, `ObjectsAllocatedByClass` являются приблизительными. Для точного числа счетчиков используйте параметр [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).  
  
 `classIds`Массив может содержать одну или несколько записей null, если соответствующий `cObjects` массив имеет типы, выгрузка которых выполняется.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
