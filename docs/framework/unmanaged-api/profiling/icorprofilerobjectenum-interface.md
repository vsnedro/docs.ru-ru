---
description: 'Дополнительные сведения о: интерфейс ICorProfilerObjectEnum'
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
ms.openlocfilehash: a41900c104818566704af0070a8cd3c6cf1bba8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781367"
---
# <a name="icorprofilerobjectenum-interface"></a>Интерфейс ICorProfilerObjectEnum

Предоставляет методы для последовательного прохода по коллекции замороженных объектов, созданных [Ngen.exe (генератор образов в машинном код)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icorprofilerobjectenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerObjectEnum`.|  
|[Метод GetCount](icorprofilerobjectenum-getcount-method.md)|Возвращает общее число замороженных объектов в коллекции.|  
|[Следующий метод](icorprofilerobjectenum-next-method.md)|Возвращает указанное количество смежных объектов из последовательной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](icorprofilerobjectenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](icorprofilerobjectenum-skip-method.md)|Перемещает курсор этого перечислителя из текущей позиции, чтобы было пропущено указанное число элементов.|  
  
## <a name="remarks"></a>Remarks  

 Интерфейс `ICorProfilerObjectEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получатель может явно управлять потоком элементов массива, тем самым избегая проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
 Чтобы получить указатель на интерфейс, используйте [ICorProfilerInfo2:: EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md) `ICorProfilerObjectEnum` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Метод EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)
