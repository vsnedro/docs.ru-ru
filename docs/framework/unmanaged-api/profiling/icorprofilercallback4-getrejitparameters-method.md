---
description: 'Дополнительные сведения о методе: ICorProfilerCallback4:: Жетрежитпараметерс'
title: Метод ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: f8dbf2c6ae80e41b8427fdaf0ef617a83138bb14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788765"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>Метод ICorProfilerCallback4::GetReJITParameters

Позволяет профилировщику кода устанавливать альтернативные флаги создания кода для нового текста перекомпилированного метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleID`  
 окне Модуль, содержащий метод, для которого среда CLR требует параметры JIT-компиляции.  
  
 `methodId`  
 окне `MethodDef` Метод, для которого среда CLR требует параметры JIT-компиляции.  
  
 `pFunctionControl`  
 окне Указатель на интерфейс [икорпрофилерфунктионконтрол](icorprofilerfunctioncontrol-interface.md) , который профилировщик может использовать для предоставления сведений о JIT-компиляции для метода, для которого выполняется повторная компиляция.  
  
## <a name="remarks"></a>Remarks  

 Среда CLR выдает `GetReJITParameters` обратный вызов, чтобы профилировщик мог указать параметры для перекомпиляции данного метода. `GetReJITParameters`Обратный вызов выдается только один раз для каждой функции; параметры, предоставляемые профилировщиком, применяются ко всем экземплярам этой функции.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
- [Метод ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)
