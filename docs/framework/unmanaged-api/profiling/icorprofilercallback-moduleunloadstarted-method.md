---
title: Метод ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: c7ad94bf766e0fcdbff95b0766cf68c2196a2c71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503341"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a>Метод ICorProfilerCallback::ModuleUnloadStarted
Уведомляет профилировщик о выгрузке модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор выгружается модуля.  
  
## <a name="remarks"></a>Примечания  
 Значение недопустимо `moduleId` для информационного запроса после `ModuleUnloadStarted` возврата метода — это последний шанс профилировщика получить сведения об этом модуле.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ModuleUnloadFinished](icorprofilercallback-moduleunloadfinished-method.md)
