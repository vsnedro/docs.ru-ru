---
description: 'Дополнительные сведения о: интерфейс ICorProfilerInfo6'
title: Интерфейс ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: c093930b102ca99a8524e6d5d6129690f80a5353
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737159"
---
# <a name="icorprofilerinfo6-interface"></a>Интерфейс ICorProfilerInfo6

[Поддерживается в платформа .NET Framework 4,6 и более поздних версиях]  
  
 Подкласс [ICorProfilerInfo5](icorprofilerinfo5-interface.md) , предоставляющий перечислитель для всех методов, определенных в заданном модуле NGen, и встроенный метод.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Возвращает перечислитель для всех методов, принадлежащих заданному модулю NGen и встроенных в тело данного метода.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
