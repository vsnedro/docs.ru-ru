---
title: Метод ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: 3ebf4a7706b3d3495e4a617b4f86a50281115436
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496559"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a>Метод ICorProfilerInfo3::EnumJITedFunctions
Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .  
  
## <a name="remarks"></a>Примечания  
 Этот метод может пересекаться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) . Перечислитель, возвращаемый этим методом, не включает функции, загруженные из образов в машинном кодах, созданных с помощью Ngen. exe.  
  
> [!NOTE]
> Возвращаемое перечисление содержит только значение "0" для значения `COR_PRF_FUNCTION::reJitId` поля.  Если требуются допустимые `COR_PRF_FUNCTION::reJitId` значения, используйте метод [метод icorprofilerinfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
