---
description: 'Дополнительные сведения о методе: ICorProfilerInfo3:: GetFunctionTailcall3Info'
title: Метод ICorProfilerInfo3::GetFunctionTailcall3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: a8976a11cf7a2c556afa62a559e3a294d81b9a1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646807"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a>Метод ICorProfilerInfo3::GetFunctionTailcall3Info

Предоставляет кадр стека функции, о которой сообщается профилировщику функцией [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) . Этот метод может быть вызван только во время обратного вызова `FunctionTailcall3WithInfo`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Возвращаемое значение `FunctionID` функции.  
  
 `eltInfo`  
 [in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека. Профилировщик должен предоставить `eltInfo` профилировщику тот же, который был передан `FunctionTailcall3WithInfo` функцией.  
  
 `pFrameInfo`  
 [out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека. Этот дескриптор допустим только во время обратного вызова `FunctionTailcall3WithInfo`, в котором профилировщик вызывал метод `GetFunctionTailcall3Info`.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
