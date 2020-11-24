---
title: Метод ICorProfilerCallback4::SurvivingReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: fb10057a406bd2192e0da61f916f81697dfa4a7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689320"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a>Метод ICorProfilerCallback4::SurvivingReferences2

Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия. Этот метод вызывается, если профилировщик реализовал интерфейс [ICorProfilerCallback4](icorprofilercallback4-interface.md) . Этот обратный вызов заменяет метод [ICorProfilerCallback2:: SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) , так как он может сообщать о больших диапазонах объектов, длина которых превышает то, что может быть выражено в ulong.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Параметры  

 `cSurvivingObjectIDRanges`  
 [in] Количество блоков смежных объектов, оставшихся в результате сборки мусора без сжатия. То есть значение `cSurvivingObjectIDRanges` является размером массивов `objectIDRangeStart` и `cObjectIDRangeLength`, в которых хранятся идентификаторы `ObjectID` и длины каждого блока объектов соответственно.  
  
 Следующие два аргумента `SurvivingReferences2` являются параллельными массивами. Иными словами, `objectIDRangeStart` и `cObjectIDRangeLength` относятся к одному и тому же блоку смежных объектов.  
  
 `objectIDRangeStart`  
 [in] Массив значений `ObjectID`, каждое из которых является начальным адресом блока смежных активных объектов в памяти.  
  
 `cObjectIDRangeLength`  
 [in] Массив целых чисел, каждое из которых представляет размер оставшегося блока смежных объектов в памяти.  
  
 Размер указывается для каждого блока, ссылка на который имеется в массиве `objectIDRangeStart`.  
  
## <a name="remarks"></a>Комментарии  

 Для определения того, уцелел ли объект после сборки мусора, элементы массивов `objectIDRangeStart` и `cObjectIDRangeLength` должны интерпретироваться следующим образом. Предположим, что значение `ObjectID` (`ObjectID`) находится в следующем диапазоне:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 При любом значении `i`, находящемся в указанном ниже диапазоне, объект уцелел после сборки мусора.  
  
 0 <= `i` < `cSurvivingObjectIDRanges`  
  
 Сборка мусора без сжатия освобождает память, занятую "мертвыми" объектами, но не сжимает освобожденное пространство. В результате этого память возвращается в кучу, но активные объекты не перемещаются.  
  
 Среда CLR вызывает метод `SurvivingReferences2` для выполнения сборки мусора без сжатия. Для сжатия сборок мусора вместо нее вызывается [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) . Отдельная операция сборки мусора может предусматривать сжатие для одного поколения и не предусматривать — для другого. Для сборки мусора в любом конкретном поколении профилировщик получит либо обратный вызов `SurvivingReferences2` , либо обратный вызов [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) , но не оба.  
  
 Несколько обратных вызовов `SurvivingReferences2` может быть получено в ходе определенной сборки мусора из-за ограниченной внутренней буферизации, нескольких обратных вызовов во время сборки мусора на сервере и по другим причинам. При получении нескольких обратных вызовов во время сборки мусора информация накапливается — все ссылки, сообщаемые в обратных вызовах `SurvivingReferences2`, сохранятся после сборки мусора.  
  
 Если профилировщик реализует интерфейсы [ICorProfilerCallback](icorprofilercallback-interface.md) и [ICorProfilerCallback4](icorprofilercallback4-interface.md) , `SurvivingReferences2` метод вызывается перед методом [ICorProfilerCallback2:: SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) , но только в случае `SurvivingReferences2` успешного возврата. Профилировщики могут возвращать значение HRESULT, указывающее на сбой метода `SurvivingReferences2`, что позволяет избежать вызова второго метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
