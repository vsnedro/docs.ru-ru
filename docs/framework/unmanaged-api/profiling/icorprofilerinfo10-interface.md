---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 7e483bae9b7898e25c376fa92d0449fc49c6f9ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548690"
---
# <a name="icorprofilerinfo10-interface"></a>Интерфейс ICorProfilerInfo10

Подкласс [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , предоставляющий методы для изменения Il функции, запроса сведений из среды выполнения, а также приостановки и возобновления работы среды выполнения.

## <a name="methods"></a>Методы  

| Метод|Описание|  
| ------------|-----------------|  
|[Метод EnumerateObjectReferences](icorprofilerinfo10-enumerateobjectreferences-method.md)|При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются). |
|[Метод IsFrozenObject](icorprofilerinfo10-isfrozenobject-method.md)|Определяет, находится ли объект в сегменте, доступном только для чтения. |
|[Метод GetLOHObjectSizeThreshold](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Возвращает значение заданного порога LOH. |
|[Метод RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md)| Режитс запрошенные методы, а также любые запрашиваются методы.  |
|[Метод SuspendRuntime](icorprofilerinfo10-suspendruntime-method.md)| Приостанавливает выполнение среды выполнения без выполнения сборки мусора. |
|[Метод ResumeRuntime](icorprofilerinfo10-resumeruntime-method.md)| Возобновляет работу среды выполнения без выполнения сборки мусора. |

## <a name="requirements"></a>Требования  
**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).  
**Заголовок:** CorProf.idl, CorProf.h  
**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
