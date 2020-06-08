---
title: Метод ICorProfilerInfo4::EnumJITedFunctions2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 2c4a89d5f96ef572518f25bf58a0005454f8e3f0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496134"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a>Метод ICorProfilerInfo4::EnumJITedFunctions2
Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы. Этот метод заменяет метод [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , который не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .  
  
## <a name="remarks"></a>Примечания  
 Этот метод может пересекаться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) . Возвращаемое перечисление содержит значения для `COR_PRF_FUNCTION::reJitId` поля. Метод [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , который заменяет этот метод, не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора, поскольку `COR_PRF_FUNCTION::reJitId` поле всегда имеет значение 0. `ICorProfilerInfo4::EnumJITedFunctions`Метод выполняет перечисление идентификаторов, перекомпилированных JIT-компилятором, так как `COR_PRF_FUNCTION::reJitId` поле задано правильно. Обратите внимание, что метод [метод icorprofilerinfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) может запускать сборку мусора, в то время как [метод ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) не будет.  Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)
- [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
