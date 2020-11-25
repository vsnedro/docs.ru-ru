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
ms.openlocfilehash: e9c7186b3217c29805327e6c1d6b10f580c3a9e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725460"
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
  
## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
