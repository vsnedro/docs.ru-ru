---
title: Интерфейс ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: 9a49d8e1ff31942c6564ab560d6726b9ede26466
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499146"
---
# <a name="icorprofilercallback7-interface"></a>Интерфейс ICorProfilerCallback7
[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Подкласс [ICorProfilerCallback6](icorprofilercallback6-interface.md) , который предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика, что обновляется поток символов, связанный с модулем в памяти.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|Уведомляет профилировщик об обновлении потока символов, связанного с модулем в памяти.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
