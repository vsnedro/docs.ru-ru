---
description: 'Дополнительные сведения о методе: ICorProfilerCallback4:: ReJITCompilationStarted'
title: Метод ICorProfilerCallback4::ReJITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: 7656f68ff6b10dcd58e48df212a036a590d0c3b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788713"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Метод ICorProfilerCallback4::ReJITCompilationStarted

Уведомляет профилировщик о том, что JIT-компилятор начал перекомпилировать функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Идентификатор функции, которая была запущена JIT-компилятором для перекомпиляции.  
  
 `rejitId`  
 окне Идентификатор повторной компиляции новой версии функции.  
  
 `fIsSafeToBlock`  
 [входные] `true` чтобы указать, что блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. `false` чтобы указать, что блокировка не повлияет на работу среды выполнения. Значение `true` не нанесет вред исполняющей среде, но может повлиять на результаты профилирования.  
  
## <a name="remarks"></a>Remarks  

 Можно получить несколько `ReJITCompilationStarted` вызовов методов и [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md) для каждой из функций, поскольку среда выполнения обрабатывает конструкторы классов. Например, среда выполнения начинает перекомпилировать метод а, но необходимо запустить конструктор класса для класса B. Таким образом, среда выполнения перекомпилирует конструктор для класса B и запускает его. Пока конструктор выполняется, он вызывает метод а, что вызывает повторную компиляцию метода а. В этом сценарии первая перекомпиляция метода A останавливается. Однако обе попытки перекомпилировать метод а сообщают о событиях JIT-компиляции.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT-компиляции в случаях, когда два потока одновременно осуществляют обратные вызовы. Например, поток A вызывает метод, `ReJITCompilationStarted` но до того, как поток a вызовет [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает метод [ICorProfilerCallback:: ексцептионсеарчфунктионентер](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из `ReJITCompilationStarted` обратного вызова для потока а. Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md) . Однако в этом случае идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Метод JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
- [Метод ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
