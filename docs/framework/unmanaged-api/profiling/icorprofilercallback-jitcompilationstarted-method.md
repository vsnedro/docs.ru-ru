---
title: Метод ICorProfilerCallback::JITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 7ce100a68a3e2b8963ed14bbf044fa9ba11d629f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725525"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Метод ICorProfilerCallback::JITCompilationStarted

Уведомляет профилировщик о том, что JIT-компилятор начал компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Идентификатор функции, для которой начинается компиляция.  
  
 `fIsSafeToBlock`  
 окне Значение, указывающее профилировщику, будет ли блокировка влиять на работу среды выполнения. Значение равно `true` , если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова; в противном случае — `false` .  
  
 Хотя значение `true` не будет нанести вред среде выполнения, оно может наклонять результаты профилирования.  
  
## <a name="remarks"></a>Комментарии  

 Можно получить более одной пары `JITCompilationStarted` вызовов и [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов. Например, среда выполнения начинает JIT-компилировать метод а, но необходимо запустить конструктор класса B. Поэтому среда выполнения JIT компилирует конструктор для класса B и запускает его. Пока конструктор выполняется, он вызывает метод а, что вызывает повторную JIT-компиляцию метода. В этом сценарии первая JIT-компиляция метода A останавливается. Однако обе попытки JIT-компиляции метода A сообщаются с событиями JIT-компиляции. Если профилировщик будет заменять код промежуточного языка MSIL для метода а путем вызова метода [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) , он должен сделать это для обоих `JITCompilationStarted` событий, но может использовать один и тот же блок MSIL для обоих.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, когда два потока одновременно осуществляют обратные вызовы. Например, поток A вызывает `JITCompilationStarted` . Однако перед вызовом потока A `JITCompilationFinished` поток B вызывает [ICorProfilerCallback:: ЕКСЦЕПТИОНСЕАРЧФУНКТИОНЕНТЕР](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из `JITCompilationStarted` обратного вызова потока A. Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку `JITCompilationFinished` профилировщик еще не получил вызов. Однако в таком случае идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
