---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: JITFunctionPitched'
title: Метод ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 11729de2188fe2f2cec7ec16ff7a5d1928cbd75d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705724"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>Метод ICorProfilerCallback::JITFunctionPitched

Оповещает профилировщик о том, что JIT-скомпилированная функция была удалена из памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Идентификатор удаленной функции.  
  
## <a name="remarks"></a>Remarks  

 Если вызывается Удаленная функция, профилировщик получит новые события JIT-компиляции при повторной компиляции функции. В настоящее время JIT-компилятор среды CLR не удаляет функции из памяти, поэтому этот обратный вызов сейчас не используется и не будет получен профилировщиком.  
  
 Значение недопустимо `functionId` до повторной компиляции функции. При повторной компиляции функции `functionId` будет использоваться то же значение.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
