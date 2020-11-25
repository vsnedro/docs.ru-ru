---
title: Метод ICorProfilerInfo3::RequestProfilerDetach
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.RequestProfilerDetach Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type:
- apiref
ms.openlocfilehash: 2ea39c94a5a0f3d24d4123d6405115ac75105e26
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721586"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>Метод ICorProfilerInfo3::RequestProfilerDetach

Дает среде выполнения команду на отключение профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwExpectedCompletionMilliseconds`  
 [in] Время в миллисекундах, которое должна ожидать среда CLR, прежде чем проверить, безопасно ли выгружать профилировщик.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Запрос отсоединения является допустимым, и процедура отсоединения теперь продолжается в другом потоке. После полного выполнения отсоединения выдается событие `ProfilerDetachSucceeded`.|  
|E_CORPROF_E_CALLBACK3_REQUIRED|Профилировщику не удалось выполнить попытку [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) для интерфейса [ICorProfilerCallback3](icorprofilercallback3-interface.md) , который он должен реализовать для поддержки операции отсоединения. Попытка отсоединения не выполнялась.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|Отсоединение невозможно, так как профилировщик установил неизменяемые флаги во время запуска. Попытка отсоединения не выполнялась; профилировщик по-прежнему полностью присоединен.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Отсоединение невозможно, так как профилировщик использовал инструментированный код языка MSIL или вставленные `enter` / `leave` обработчики. Попытка отсоединения не выполнялась; профилировщик по-прежнему полностью присоединен.<br /><br /> **Примечание** . Инструментированный MSIL — это код, предоставляемый профилировщиком с помощью метода [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) .|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Среда выполнения еще не была инициализирована в управляемом приложении. (То есть среда выполнения не была полностью загружена.) Этот код ошибки может быть возвращен, когда запрос отсоединения запрашивается в методе [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) обратного вызова профилировщика.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` был вызван в неподдерживаемое время. Это происходит, если метод вызывается в управляемом потоке, но не в методе [ICorProfilerCallback](icorprofilercallback-interface.md) или в методе [ICorProfilerCallback](icorprofilercallback-interface.md) , который не допускает сборки мусора. Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Комментарии  

 При выполнении процедуры отсоединения поток отсоединения (поток, созданный специально для отсоединения профилировщика) периодически проверяет, все ли потоки вышли из кода профилировщика. Профилировщик должен предоставить оценку, как долго это должно происходить, с помощью параметра `dwExpectedCompletionMilliseconds`. В качестве этого значения рекомендуется использовать обычное время, которое профилировщик проводит внутри любого конкретного метода `ICorProfilerCallback*`; это значение не должно быть меньше половины максимального времени, которое профилировщик предполагает потратить.  
  
 Поток отсоединения использует `dwExpectedCompletionMilliseconds`, чтобы определить продолжительность бездействия перед проверкой, был ли код обратного вызова профилировщика удален из всех стеков. Хотя сведения о следующем алгоритме могут измениться в будущих выпусках среды CLR, он иллюстрирует один из способов `dwExpectedCompletionMilliseconds`, который можно использовать при определении того, когда можно безопасно выгрузить профилировщик. Поток отсоединения сначала находится в неактивном состоянии в течение `dwExpectedCompletionMilliseconds` миллисекунд. Если после пробуждения из спящего режима среда CLR обнаруживает, что код обратного вызова профилировщика по-прежнему существует, поток отсоединения в спящий режим снова будет выполняться в два раза больше `dwExpectedCompletionMilliseconds` миллисекунд. Если после выхода из этого второго неактивного состояния поток отсоединения обнаруживает, что код обратного вызова профилировщика все еще присутствует, то он бездействует в течение 10 минут перед еще одной проверкой. Поток отсоединения продолжает выполнять очередную проверку каждые 10 минут.  
  
 Если профилировщик указывает `dwExpectedCompletionMilliseconds` как 0 (ноль), среда CLR использует значение по умолчанию 5000, которое означает, что проверка будет выполняться через 5 секунд, следующая проверка через 10 секунд, и затем каждые 10 минут соответственно.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
