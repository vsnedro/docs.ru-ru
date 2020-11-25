---
title: Интерфейс ICorProfilerObjectEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: 73c9f07ff9a7bffc2fb01c0dde390ca8364500b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731180"
---
# <a name="icorprofilerobjectenum-interface"></a>Интерфейс ICorProfilerObjectEnum

Предоставляет методы для последовательного прохода по коллекции замороженных объектов, созданных [Ngen.exe (генератор образов в машинном код)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icorprofilerobjectenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerObjectEnum`.|  
|[Метод GetCount](icorprofilerobjectenum-getcount-method.md)|Возвращает общее число замороженных объектов в коллекции.|  
|[Метод Next](icorprofilerobjectenum-next-method.md)|Возвращает указанное количество смежных объектов из последовательной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](icorprofilerobjectenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](icorprofilerobjectenum-skip-method.md)|Перемещает курсор этого перечислителя из текущей позиции, чтобы было пропущено указанное число элементов.|  
  
## <a name="remarks"></a>Комментарии  

 Интерфейс `ICorProfilerObjectEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получатель может явно управлять потоком элементов массива, тем самым избегая проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
 Чтобы получить указатель на интерфейс, используйте [ICorProfilerInfo2:: EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md) `ICorProfilerObjectEnum` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Метод EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)
