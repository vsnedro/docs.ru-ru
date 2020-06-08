---
title: Метод ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 08337a118a80d213f16e2a16f744b96f5dde2e7f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497009"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>Метод ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
Получает собственный адрес и сведения о кадре для предложения исключения ( `catch` / `finally` / `filter` ), которое будет запущено или только что было запущено.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Параметры  
 `pinfo`  
 заполняет Указатель на структуру [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) , описывающую экземпляр предложения текущего исключения и связанный с ним кадр.  
  
## <a name="remarks"></a>Примечания  
 При получении уведомления об исключении `GetNotifiedExceptionClauseInfo` можно использовать для получения собственного адреса и сведений о кадре для предложения исключения ( `catch` / `finally` / `filter` ), которое будет выполнено (в результате выполнения выражения[ICorProfilerCallback:: ексцептионкатчерентер](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ексцептионунвиндфиналлентер](icorprofilercallback-exceptionunwindfinallyenter-method.md)или [ICorProfilerCallback:: ексцептионсеарчфилтерентер](icorprofilercallback-exceptionsearchfilterenter-method.md) получено профилировщиком) или только что выполнялся (в профилировщике получен обратный вызов ICorProfilerCallback:[: ексцептионкатчерлеаве](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: exceptionunwindfinallyleave-](icorprofilercallback-exceptionunwindfinallyleave-method.md)или [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) ).  
  
 Этот вызов можно выполнить в любое время после одного из обратных вызовов при вводе выше, пока не будет получен соответствующий обратный вызов метода Leave или не будет создано вложенное исключение в текущем предложении, в этом случае для этого предложения нет уведомления о выходе. Обратите внимание, что выдаваемое исключение не может быть экранировано `filter` предложением исключения, поэтому в этом случае всегда отображается уведомление о выходе.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
