---
title: Метод ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500381"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a>Метод ICorProfilerCallback::ClassUnloadFinished
Уведомляет профилировщик о завершении выгрузки класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Параметры

- `classId`

  \[в] определяет класс, который был выгружен.

- `hrStatus`

  \[in] значение HRESULT, указывающее, успешно ли выгружен класс.
  
## <a name="remarks"></a>Примечания  
 Некоторые части выгрузки класса могут продолжаться после `ClassUnloadFinished` обратного вызова. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть выгрузки класса успешно выполнена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)
