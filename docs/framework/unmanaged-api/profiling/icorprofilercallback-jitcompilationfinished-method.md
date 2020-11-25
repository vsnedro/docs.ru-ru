---
title: Метод ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 98e81d2d02a9495b678d49fb916f99068dd604f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725538"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>Метод ICorProfilerCallback::JITCompilationFinished

Уведомляет профилировщик о том, что JIT-компилятор завершил компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры

- `functionId`

  \[in] идентификатор скомпилированной функции.

- `hrStatus`

  \[в] значение, указывающее, успешно ли выполнена компиляция.

- `fIsSafeToBlock`

  \[в] значение, указывающее профилировщику, будет ли блокировка влиять на работу среды выполнения. Значение равно `true` , если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова; в противном случае — `false` .

  Хотя значение `true` не будет нанести вред среде выполнения, оно может наклонять результаты профилирования.

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
