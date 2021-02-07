---
description: 'Дополнительные сведения о: интерфейс ICorProfilerInfo7'
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 7a33472d5562ad57d38291c64f8da7021ae2fe91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737081"
---
# <a name="icorprofilerinfo7-interface"></a>Интерфейс ICorProfilerInfo7

[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Подкласс [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь заданных метаданных к модулю и предоставляющий доступ к потоку символов в памяти.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ApplyMetaData](icorprofilerinfo7-applymetadata-method.md)|Применяет метаданные, которые были недавно определены `IMetadataEmit::Define*` методами, к указанному модулю.|  
|[Метод GetInMemorySymbolsLength](icorprofilerinfo7-getinmemorysymbolslength-method.md)|Возвращает длину потока символов в памяти.|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|Считывает байты из потока символов в памяти.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
