---
title: Интерфейс ICorProfilerCallback6
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 2176b624a427994b9d2af4b5eba31a64c9288a0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725473"
---
# <a name="icorprofilercallback6-interface"></a>Интерфейс ICorProfilerCallback6

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Подкласс [ICorProfilerCallback5](icorprofilercallback5-interface.md) , предоставляющий метод обратного вызова, который среда CLR использует для уведомления профилировщика о загрузке сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)|Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
