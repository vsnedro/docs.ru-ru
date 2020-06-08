---
title: Метод ICorProfilerInfo3::SetFunctionIDMapper2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 723cb277a7df592e0494505018f7422e4e40f5f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496156"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>Метод ICorProfilerInfo3::SetFunctionIDMapper2
Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика. Этот метод расширяет метод [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) с дополнительным параметром данных, который профилировщики могут использовать для устранения неоднозначности между средами выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>Параметры  
 `pFunc`  
 окне Указатель на реализацию [FunctionIDMapper2](functionidmapper2-function.md) , которая будет вызываться для соответствия `FunctionID` значений их альтернативным значениям.  
  
 `clientData`  
 окне Указатель, который передается в каждый вызов функции [FunctionIDMapper2](functionidmapper2-function.md) , выполненной текущей средой выполнения. Профилировщик может использовать эти сведения для устранения неоднозначности между средами выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="remarks"></a>Примечания  
 Альтернативы значениям FunctionID будут переданы обработчикам входа и выхода функций профилировщика ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)и [FunctionTailcall3](functiontailcall3-function.md); или [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)), которые указаны в методе [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) или [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .  
  
 `FunctionIDMapper2`Метод можно задать только один раз. рекомендуется задать его в обратном вызове метода [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
