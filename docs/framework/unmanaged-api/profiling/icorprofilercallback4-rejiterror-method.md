---
title: Метод ICorProfilerCallback4::ReJITError
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 46312aaf530e69f0e6a90e35515f1373d01b4340
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730244"
---
# <a name="icorprofilercallback4rejiterror-method"></a>Метод ICorProfilerCallback4::ReJITError

Уведомляет профилировщик о том, что компилятор JIT обнаружил ошибку в процессе перекомпиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleID`  
 окне Объект, `ModuleID` в котором была выполнена повторная попытка повторной компиляции.  
  
 `methodId`  
 окне `MethodDef` Метод метода, для которого была выполнена попытка повторной компиляции.  
  
 `functionId`  
 окне Экземпляр функции, который перекомпилируется или помечен для повторной компиляции. Это значение может быть `NULL` , если ошибка возникла для каждого метода, а не для каждого экземпляра (например, если профилировщик указал недопустимый токен метаданных для повторной компиляции метода).  
  
 `hrStatus`  
 окне Значение HRESULT, указывающее природу сбоя. Список значений см. в разделе Status HRESULTs.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Значения, возвращаемые из этого обратного вызова, игнорируются.  
  
## <a name="status-hresults"></a>Значения HRESULT для состояния  
  
|Массив значений HRESULT для состояния|Описание|  
|--------------------------|-----------------|  
|E_INVALIDARG|`moduleID`Токен или `methodDef` имеет значение `NULL` .|  
|CORPROF_E_DATAINCOMPLETE|Модуль еще не полностью загружен или находится в процессе выгрузки.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Указанный модуль был динамически создан (например, by `Reflection.Emit` ) и поэтому не поддерживается этим методом.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Экземпляр метода создается в собираемой сборке и поэтому не может быть перекомпилирован. Обратите внимание, что типы и функции, определенные в контексте, не являющемся контекстом отражения (например, `List<MyCollectibleStruct>` ), можно создать в собираемой сборке.|  
|E_OUTOFMEMORY|В среде CLR возникла нехватка памяти при попытке пометить указанный метод для повторной компиляции JIT.|  
|Другое|Операционная система возвратила сбой за пределами среды CLR. Например, если системный вызов для изменения защиты доступа к странице памяти завершается ошибкой, отображается сообщение об ошибке операционной системы.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
