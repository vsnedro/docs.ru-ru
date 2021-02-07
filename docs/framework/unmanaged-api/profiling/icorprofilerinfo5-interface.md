---
description: 'Дополнительные сведения о: интерфейс ICorProfilerInfo5'
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
ms.openlocfilehash: c89faf3db08adeee3ffcfbb755a5da5ae44b3c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737276"
---
# <a name="icorprofilerinfo5-interface"></a>Интерфейс ICorProfilerInfo5

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Подкласс [метод icorprofilerinfo4](icorprofilerinfo4-interface.md) , предоставляющий методы для использования профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)|Получает текущие категории событий, о которых профилировщик хочет принимать уведомления из среды CLR.|  
|[Метод SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)|Определяет значение, указывающее типы событий, для которых профилировщик хочет принимать уведомления о событиях от среды CLR.|  
  
## <a name="remarks"></a>Remarks  

 Методы, доступные в этом интерфейсе, предназначены для замены методов [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) и [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
