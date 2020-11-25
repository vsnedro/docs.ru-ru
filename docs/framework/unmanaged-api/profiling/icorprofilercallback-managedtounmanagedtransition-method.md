---
title: Метод ICorProfilerCallback::ManagedToUnmanagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: ef65ed908c71bcc2755aaf42070439fd7dab3f6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733143"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>Метод ICorProfilerCallback::ManagedToUnmanagedTransition

Уведомляет профилировщик о том, что произошел переход из управляемого кода в неуправляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Идентификатор вызываемой функции.  
  
 `reason`  
 окне Значение перечисления [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) , указывающее, произошло ли переход из-за вызова неуправляемого кода из управляемого кода или из-за возврата из управляемой функции, вызываемой неуправляемой функцией.  
  
## <a name="remarks"></a>Комментарии  

 Если значение `reason` равно COR_PRF_TRANSITION_CALL, идентификатором функции является неуправляемая функция, которая никогда не будет компилироваться с помощью JIT-компилятора. С неуправляемыми функциями связаны основные сведения, такие как имя и некоторые метаданные. Если неуправляемая функция была вызвана с помощью неявного вызова платформы (PInvoke), среда выполнения не может определить назначение вызова, а значение `functionId` будет равно null. Дополнительные сведения о неявном вызове PInvoke см. в разделе [использование взаимодействия C++ (неявный PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [Использование явного вызова PInvoke в C++ (атрибут DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
