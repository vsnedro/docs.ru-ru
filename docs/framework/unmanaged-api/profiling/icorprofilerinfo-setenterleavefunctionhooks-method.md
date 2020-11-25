---
title: Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 18aed5c5314fc1057767b599c538952a1d4d6b57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722236"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks

Задает реализованные профилировщиком функции, которые должны вызываться для обработчиков "Ввод", "Leave" и "таилкалл" управляемых функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Параметры  

 `pFuncEnter`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionEnter](functionenter-function.md) .  
  
 `pFuncLeave`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionLeave](functionleave-function.md) .  
  
 `pFuncTailcall`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [функтионтаилкалл](functiontailcall-function.md) .  
  
## <a name="remarks"></a>Комментарии  

 В .NET Framework версии 1,0 каждый указатель функции может иметь значение null, чтобы отключить соответствующий обратный вызов.  
  
 Одновременно может быть активным только один набор обратных вызовов. Таким образом, если профилировщик вызывает `SetEnterLeaveFunctionHooks` и [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), то `SetEnterLeaveFunctionHooks2` имеет приоритет.  
  
 `SetEnterLeaveFunctionHooks`Метод может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
