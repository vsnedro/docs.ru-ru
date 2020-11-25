---
title: Метод ICorProfilerCallback4::ReJITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: a6c2209433a652523fd8e3a7cc2db1272600e1bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730270"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a>Метод ICorProfilerCallback4::ReJITCompilationFinished

Уведомляет профилировщик о том, что JIT-компилятор завершил повторную компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Идентификатор перекомпилированной функции.  
  
 `rejitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.  
  
 `hrStatus`  
 окне Значение, указывающее, успешно ли выполнена повторная компиляция JIT.  
  
 `fIsSafeToBlock`  
 [входные] `true` чтобы указать, что блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. `false` чтобы указать, что блокировка не повлияет на работу среды выполнения.  
  
 Значение `true` не нанесет вред исполняющей среде, но может повлиять на результаты профилирования.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
- [Метод ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)
