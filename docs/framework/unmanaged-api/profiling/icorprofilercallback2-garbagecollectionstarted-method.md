---
title: Метод ICorProfilerCallback2::GarbageCollectionStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: 63a8d212a61bd73f44995f0e057eeff96f9a5554
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731960"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Метод ICorProfilerCallback2::GarbageCollectionStarted

Уведомляет профилировщик кода о начале сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Параметры  

 `cGenerations`  
 окне Общее число записей в `generationCollected` массиве.  
  
 `generationCollected`  
 окне Массив логических значений, которые относятся к `true` сбору данных, соответствующих индексу массива, при сборе мусора; в противном случае — значение `false` .  
  
 Массив индексируется по значению перечисления [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , которое указывает на поколение.  
  
 `reason`  
 окне Значение перечисления [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) , указывающее причину принудительной сборки мусора.  
  
## <a name="remarks"></a>Комментарии  

 Все обратные вызовы, относящиеся к этой сборке мусора, будут выполняться между `GarbageCollectionStarted` обратным вызовом и соответствующим обратным вызовом [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) . Эти обратные вызовы не должны выполняться в одном потоке.  
  
 Профилировщик может быть в безопасности проверять объекты в исходных расположениях во время `GarbageCollectionStarted` обратного вызова. Сборщик мусора начнет перемещать объекты после возврата из `GarbageCollectionStarted` . После возвращения профилировщика из этого обратного вызова профилировщик должен рассматривать все идентификаторы объектов как недопустимые до получения `ICorProfilerCallback2::GarbageCollectionFinished` обратного вызова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
