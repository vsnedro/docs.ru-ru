---
title: Метод ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 26df1599af247bd08d3702d4ef3c5aa2f648620c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720377"
---
# <a name="icorprofilercallbackinitialize-method"></a>Метод ICorProfilerCallback::Initialize

Вызывается для инициализации профилировщика кода при запуске нового приложения среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Параметры

- `pICorProfilerInfoUnk`

  \[в] указатель на интерфейс [IUnknown](/cpp/atl/iunknown) , который профилировщик должен запрашивать для указателя интерфейса [ICorProfilerInfo](icorprofilerinfo-interface.md) .  

## <a name="remarks"></a>Комментарии  

 `Initialize`Вызов является единственной возможностью включать (или отключать) обратные вызовы, которые являются неизменяемыми. После включения обратного вызова в `Initialize` вызове он не может быть отключен позже с помощью команды [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Значение COR_PRF_MONITOR_IMMUTABLE перечисления [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) указывает, какие события являются неизменяемыми.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод Shutdown](icorprofilercallback-shutdown-method.md)
