---
title: Интерфейс ICorProfilerThreadEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: d28991254fba73de7a55135844d16417580d8792
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494388"
---
# <a name="icorprofilerthreadenum-interface"></a>Интерфейс ICorProfilerThreadEnum
Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icorprofilerthreadenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerThreadEnum`.|  
|[Метод GetCount](icorprofilerthreadenum-getcount-method.md)|Возвращает число потоков, используемых приложением.|  
|[Метод Next](icorprofilerthreadenum-next-method.md)|Возвращает заданное число смежных потоков из упорядоченной коллекции потоков начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](icorprofilerthreadenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](icorprofilerthreadenum-skip-method.md)|Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.|  
  
## <a name="remarks"></a>Примечания  
 Интерфейс `ICorProfilerThreadEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
