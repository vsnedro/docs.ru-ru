---
title: Метод ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 2d084ce0a785ba37c5b7dc937ed116cee74b7594
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720676"
---
# <a name="icorprofilercallbackrootreferences-method"></a>Метод ICorProfilerCallback::RootReferences

Уведомляет профилировщик о получении сведений о корневых ссылках после сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Параметры  

 `cRootRefs`  
 окне Число ссылок в `rootRefIds` массиве.  
  
 `rootRefIds`  
 окне Массив идентификаторов объектов, ссылающихся либо на статический объект, либо на объект в стеке.  
  
## <a name="remarks"></a>Комментарии  

 `RootReferences`Для уведомления профилировщика вызываются методы и [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) . Профилировщики обычно реализуют один или другой, но не оба, так как передаваемые сведения `RootReferences2` являются надмножеством переданного `RootReferences` .  
  
 `rootRefIds`Массив может содержать пустой объект. Например, все ссылки на объекты, объявленные в стеке, рассматриваются сборщиком мусора как корни и всегда будут сообщать о них.  
  
 Идентификаторы объектов, возвращаемые, `RootReferences` недопустимы во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старых адресов в новые адреса. Таким образом, профилировщики не должны пытаться проверять объекты во время `RootReferences` вызова. При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) все объекты были перемещены в новые расположения и могут быть безопасно проверены.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
