---
title: Интерфейс ICorProfilerInfo5
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495631"
---
# <a name="icorprofilerinfo5-interface"></a>Интерфейс ICorProfilerInfo5
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Подкласс [метод icorprofilerinfo4](icorprofilerinfo4-interface.md) , предоставляющий методы для использования профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)|Получает текущие категории событий, о которых профилировщик хочет принимать уведомления из среды CLR.|  
|[Метод SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)|Определяет значение, указывающее типы событий, для которых профилировщик хочет принимать уведомления о событиях от среды CLR.|  
  
## <a name="remarks"></a>Примечания  
 Методы, доступные в этом интерфейсе, предназначены для замены методов [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) и [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
