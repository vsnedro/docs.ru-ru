---
title: Метод ICorProfilerCallback::ExceptionSearchFilterEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
ms.openlocfilehash: 304b8da670786851a70e38e6623d44b1bde71a04
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500238"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a>Метод ICorProfilerCallback::ExceptionSearchFilterEnter
Уведомляет профилировщик о том, что фаза поиска обработки исключений начала выполнять пользовательский фильтр исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Параметры

- `functionId`

  \[in] идентификатор функции, которая содержит фильтр.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)
