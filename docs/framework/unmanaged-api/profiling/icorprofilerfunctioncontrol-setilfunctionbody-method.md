---
title: Метод ICorProfilerFunctionControl::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: a6b24fd59a183a4a59b117663772417d55cc67db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503148"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>Метод ICorProfilerFunctionControl::SetILFunctionBody
Заменяет тело метода на языке CIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbNewILMethodHeader`  
 [in] Общий размер нового кода CIL, включая заголовок и все структуры после тела.  
  
 `pbNewILMethodHeader`  
 [in] Указатель на новый заголовок на языке CIL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие специфичные результаты HRESULT.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Замена выполнена успешно.|  
  
## <a name="remarks"></a>Примечания  
 В отличие от метода [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) `SetILFunctionBody` метод управляет памятью, необходимой для нового тела CIL. Это означает, что тело CIL, предоставленное профилировщиком, не должно выделяться с помощью интерфейса [IMethodMalloc](imethodmalloc-interface.md) или выделено в определенном диапазоне. Его можно разместить в любой куче. Профилировщик может освободить память, используемую для его тела CIL после `SetILFunctionBody` возврата.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md)
