---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: Класслоадстартед'
title: Метод ICorProfilerCallback::ClassLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 2474f8041b0858cbcb81d3f4042f1748cb99df3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706478"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a>Метод ICorProfilerCallback::ClassLoadStarted

Уведомляет профилировщик о том, что класс загружается.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Параметры

- `classId`

  \[в] определяет класс, который загружается.

## <a name="remarks"></a>Remarks  

 Значение недопустимо `classId` для информационного запроса, пока не будет вызван метод [ICorProfilerCallback:: класслоадфинишед](icorprofilercallback-classloadfinished-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
