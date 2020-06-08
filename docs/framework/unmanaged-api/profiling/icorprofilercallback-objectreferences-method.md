---
title: Метод ICorProfilerCallback::ObjectReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 12a0792e8fafc73b480de6bacc86f98470dfedf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503293"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>Метод ICorProfilerCallback::ObjectReferences
Уведомляет профилировщик об объектах в памяти, на которые ссылается указанный объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>Параметры  
 `objectId`  
 окне Идентификатор объекта, ссылающегося на объекты.  
  
 `classId`  
 окне Идентификатор класса, экземпляр которого является указанным объектом.  
  
 `cObjectRefs`  
 окне Количество объектов, на которые ссылается указанный объект (то есть количество элементов в `objectRefIds` массиве).  
  
 `objectRefIds`  
 окне Массив идентификаторов объектов, на которые ссылается `objectId` .  
  
## <a name="remarks"></a>Примечания  
 `ObjectReferences`Метод вызывается для каждого объекта, остающегося в куче после завершения сборки мусора. Если профилировщик возвращает ошибку из этого обратного вызова, службы профилирования будут прекращены вызовом этого обратного вызова до следующей сборки мусора.  
  
 `ObjectReferences`Обратный вызов можно использовать в сочетании с обратным вызовом [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) , чтобы создать полный граф ссылки на объект для среды выполнения. Общеязыковая среда выполнения (CLR) гарантирует, что в методе каждый раз сообщается ссылка на каждый объект `ObjectReferences` .  
  
 Идентификаторы объектов, возвращаемые, `ObjectReferences` недопустимы во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов. Таким образом, профилировщики не должны пытаться проверять объекты во время `ObjectReferences` вызова. При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) сборка мусора завершается, и проверка может быть безопасно выполнена.  
  
 Значение NULL `ClassId` указывает, что `objectId` имеет тип, который выгружается.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
