---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: ObjectAllocated'
title: Метод ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 58b58aeb4bb88d0df32cebc32440317a4d23632d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745168"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>Метод ICorProfilerCallback::ObjectAllocated

Уведомляет профилировщик о том, что память в куче была выделена для объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Параметры  

 `objectId`  
 окне Идентификатор объекта, для которого была выделена память.  
  
 `classId`  
 окне Идентификатор класса, экземпляр которого является объектом.  
  
## <a name="remarks"></a>Remarks  

 `ObjectedAllocated`Метод не вызывается для выделений из стека или неуправляемой памяти. `classId`Параметр может ссылаться на класс в управляемом коде, который еще не был загружен. Профилировщик получит обратный вызов загрузки класса для этого класса сразу после `ObjectAllocated` обратного вызова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)
- [Метод ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)
