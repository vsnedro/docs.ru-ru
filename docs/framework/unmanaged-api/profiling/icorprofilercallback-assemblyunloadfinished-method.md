---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: AssemblyUnloadFinished'
title: Метод ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 30d6bd805a1466d6a65728b22f677ba00e09ffb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648029"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>Метод ICorProfilerCallback::AssemblyUnloadFinished

Уведомляет профилировщик о том, что сборка была выгружена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Параметры

- `assemblyId`

  \[в] определяет сборку, которая выгружается.

- `hrStatus`

  \[in] значение HRESULT, указывающее, успешно ли выгружена сборка.

## <a name="remarks"></a>Remarks  

 Значение недопустимо `assemblyId` для информационного запроса после возврата метода [ICorProfilerCallback:: ассемблюнлоадстартед](icorprofilercallback-assemblyunloadstarted-method.md) .  
  
 Некоторые части выгрузки сборки могут продолжаться после `AssemblyUnloadFinished` обратного вызова. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT в случае успеха в `hrStatus` указывает только на то, что первая часть выгрузки сборки завершилась успешно.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
