---
title: Метод ICorProfilerCallback::UnmanagedToManagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: 446de663d437c950f3a9be968e7dcbe8d25ed2b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717289"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>Метод ICorProfilerCallback::UnmanagedToManagedTransition

Уведомляет профилировщик о том, что произошел переход из неуправляемого кода в управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Идентификатор вызываемой функции.  
  
 `reason`  
 окне Значение перечисления [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) , указывающее, произошло ли переход из-за вызова управляемого кода из неуправляемого кода или из-за возврата из неуправляемой функции, вызванной управляемой.  
  
## <a name="remarks"></a>Комментарии  

 Если значение `reason` равно COR_PRF_TRANSITION_RETURN и `functionId` не равно null, идентификатор функции является неуправляемой функцией и никогда не будет компилироваться с помощью JIT-компилятора. С неуправляемыми функциями связаны некоторые основные сведения, такие как имя и некоторые метаданные.  
  
 Если значение `reason` равно COR_PRF_TRANSITION_CALL, возможно, что вызванная функция (то есть управляемая функция) еще не скомпилирована с помощью JIT-компилятора.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)
- [Использование явного вызова PInvoke в C++ (атрибут DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [Использование взаимодействия C++ (неявный PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
