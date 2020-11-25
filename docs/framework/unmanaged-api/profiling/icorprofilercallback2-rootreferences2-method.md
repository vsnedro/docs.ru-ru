---
title: Метод ICorProfilerCallback2::RootReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: 9e53e7bcecd900bb6c71d0a822e9b63ff6726e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729524"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>Метод ICorProfilerCallback2::RootReferences2

Уведомляет профилировщик о корневых ссылках после сборки мусора. Этот метод является расширением метода [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cRootRefs`  
 окне Число элементов в `rootRefIds` `rootKinds` `rootFlags` массивах,, и `rootIds` .  
  
 `rootRefIds`  
 окне Массив идентификаторов объектов, каждый из которых ссылается на статический объект или объект в стеке. Элементы `rootKinds` массива предоставляют сведения для классификации соответствующих элементов в `rootRefIds` массиве.  
  
 `rootKinds`  
 окне Массив значений [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) , указывающих тип корня сборки мусора.  
  
 `rootFlags`  
 окне Массив значений [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) , описывающих свойства корня сборки мусора.  
  
 `rootIds`  
 окне Массив значений UINT_PTR, указывающих на целое число, которое содержит дополнительные сведения об корне сборки мусора в зависимости от значения `rootKinds` параметра.  
  
 Если корневым типом является стек, то для функции, содержащей переменную, используется корневой идентификатор. Если этот корневой идентификатор равен 0, функция является неименованной функцией, которая является внутренней для среды CLR. Если корневой тип является обработчиком, корневой идентификатор — для обработчика сборки мусора. Для других корневых типов идентификатор является непрозрачным значением и должен игнорироваться.  
  
## <a name="remarks"></a>Комментарии  

 `rootRefIds` `rootKinds` `rootFlags` Массивы,, и `rootIds` являются параллельными массивами. То есть,,, `rootRefIds[i]` `rootKinds[i]` `rootFlags[i]` и `rootIds[i]` имеют тот же корень.  
  
 Оба `RootReferences` `RootReferences2` метода и вызываются для уведомления профилировщика. Профилировщики, как правило, реализуют один метод или другой, но не оба, так как передаваемые сведения `RootReferences2` являются надмножеством переданного `RootReferences` .  
  
 Записи в могут `rootRefIds` быть равны нулю, что означает, что соответствующая корневая ссылка имеет значение NULL и не ссылается на объект в управляемой куче.  
  
 Идентификаторы объектов, возвращаемые, `RootReferences2` недопустимы во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старых адресов в новые адреса. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `RootReferences2`. При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) все объекты были перемещены в новые расположения и могут быть безопасно проверены.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
