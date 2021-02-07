---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: JITCachedFunctionSearchStarted'
title: Метод ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: 1faaf8fbc1e0fee9ce76850cfedcd4e8cf934371
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705776"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>Метод ICorProfilerCallback::JITCachedFunctionSearchStarted

Уведомляет профилировщик о начале поиска для функции, которая была скомпилирована ранее с помощью генератора образов в машинном кодах (NGen.exe).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Параметры

- `functionId`

  \[in] идентификатор функции, для которой выполняется поиск.

- `pbUseCachedFunction`

  \[out], `true` если подсистема выполнения должна использовать кэшированную версию функции (если она доступна); в противном случае — `false` . Если значение равно `false` , подсистема выполнения JIT-компилирует функцию вместо использования версии, которая не является JIT-скомпилированной.

## <a name="remarks"></a>Remarks  

 В платформа .NET Framework версии 2,0 `JITCachedFunctionSearchStarted` обратные вызовы [методов и ICorProfilerCallback:: житкачедфунктионсеарчфинишед](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) не будут выполняться для всех функций в обычных образах Ngen. Только образы NGen, оптимизированные для профиля, будут создавать обратные вызовы для всех функций в образе. Однако из-за дополнительных издержек профилировщик должен запросить оптимизированные профилировщиком генераторы NGen только в том случае, если планируется использовать эти обратные вызовы для принудительной компиляции функции JIT (JIT). В противном случае профилировщик должен использовать отложенную стратегию для сбора сведений о функции.  
  
 Профилировщики должны поддерживать случаи, когда несколько потоков профилированного приложения одновременно вызывают один и тот же метод. Например, поток а вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, устанавливая для *пбусекачедфунктион* значение false для принудительной JIT-компиляции. Затем поток а вызывает метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).  
  
 Теперь потоки B вызывают `JITCachedFunctionSearchStarted` одну и ту же функцию. Несмотря на то, что профилировщик установил свою цель для JIT-компиляции функции, профилировщик получает второй обратный вызов, так как поток B отправляет обратный вызов до того, как профилировщик ответил на вызов потока A `JITCachedFunctionSearchStarted` . Порядок, в котором потоки выполняют вызовы, зависит от того, как запланированы потоки.  
  
 Когда профилировщик получает дублирующиеся обратные вызовы, он должен задать значение, на которое ссылается, `pbUseCachedFunction` на то же значение для всех повторяющихся обратных вызовов. То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с одним и тем же `functionId` значением, профилировщик должен каждый раз реагировать на эти же значения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
