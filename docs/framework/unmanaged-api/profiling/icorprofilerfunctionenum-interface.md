---
description: 'Дополнительные сведения о: Интерфейс ICorProfilerFunctionEnum'
title: Интерфейс ICorProfilerFunctionEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 0a9437ee1f5c481c2c2d1fd46361da6e938dd179
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737601"
---
# <a name="icorprofilerfunctionenum-interface"></a>Интерфейс ICorProfilerFunctionEnum

Предоставляет методы для последовательного перебора коллекции функций в среде CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icorprofilerfunctionenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerFunctionEnum`.|  
|[Метод GetCount](icorprofilerfunctionenum-getcount-method.md)|Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.|  
|[Следующий метод](icorprofilerfunctionenum-next-method.md)|Возвращает заданное число смежных функций из последовательной коллекции функций начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](icorprofilerfunctionenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](icorprofilerfunctionenum-skip-method.md)|Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.|  
  
## <a name="remarks"></a>Remarks  

 Интерфейс `ICorProfilerFunctionEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
 Интерфейс `ICorProfilerFunctionEnum` перечисляет функции, которые уже были скомпилированы для JIT-отладки, но не включает функции, загруженные из собственных образов, созданных с помощью программы Ngen.exe.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Метод EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)
