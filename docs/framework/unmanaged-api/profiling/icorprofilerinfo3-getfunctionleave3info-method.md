---
description: 'Дополнительные сведения о методе: ICorProfilerInfo3:: GetFunctionLeave3Info'
title: Метод ICorProfilerInfo3::GetFunctionLeave3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: 3031190a3603bedb3f58e7a86747542831c72291
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646801"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a>Метод ICorProfilerInfo3::GetFunctionLeave3Info

Предоставляет кадр стека и возвращаемое значение функции, о которой сообщается профилировщику функцией [функции FunctionLeave3WithInfo](functionleave3withinfo-function.md) . Этот метод может быть вызван только во время обратного вызова `FunctionLeave3WithInfo`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 окне Возвращаемое значение `FunctionID` функции.  
  
 `eltInfo`  
 [in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека. Профилировщик должен предоставлять те же `eltInfo` данные, что и профилировщик, с помощью функции [FunctionLeave3WithInfo](functionleave3withinfo-function.md) .  
  
 `pFrameInfo`  
 [out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека. Этот дескриптор допустим только во время обратного вызова `FunctionLeave3WithInfo`, в котором профилировщик вызывал метод `GetFunctionLeave3Info`.  
  
 `pRetvalRange`  
 заполняет Указатель на структуру [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) , которая содержит значение, возвращаемое функцией. Чтобы получить доступ к сведениям о возвращаемом значении, `COR_PRF_ENABLE_FUNCTION_RETVAL` необходимо установить флаг. Профилировщик может использовать [метод ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий.  
  
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
