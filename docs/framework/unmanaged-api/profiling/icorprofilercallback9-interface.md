---
description: 'Дополнительные сведения о: интерфейс ICorProfilerCallback9'
title: Интерфейс ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4bfcaf6f8985909ef9142ef4d08535a19facd7e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781653"
---
# <a name="icorprofilercallback9-interface"></a>Интерфейс ICorProfilerCallback9

[Поддерживается в платформа .NET Framework 4.7.2 и более поздних версиях]  

 Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод был собран в мусор и затем выгружен.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodUnloaded](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Уведомляет профилировщик о том, что динамический метод был собран в мусор и затем выгружен.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
