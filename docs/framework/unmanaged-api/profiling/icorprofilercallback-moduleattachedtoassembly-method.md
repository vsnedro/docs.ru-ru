---
title: Метод ICorProfilerCallback::ModuleAttachedToAssembly
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: 4f494919d11e0f979cf1964c08106fbb9b9ed20b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503397"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>Метод ICorProfilerCallback::ModuleAttachedToAssembly
Уведомляет профилировщик о том, что модуль присоединен к своей родительской сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор присоединяемого модуля.  
  
 `AssemblyId`  
 окне ИДЕНТИФИКАТОР родительской сборки, к которой присоединен модуль.  
  
## <a name="remarks"></a>Примечания  
 Модуль можно загрузить через таблицу адресов импорта (IAT), через вызов `LoadLibrary` или через ссылку на метаданные. В результате загрузчик среды CLR имеет несколько путей кода для определения сборки, в которой находится модуль. Таким образом, после вызова метода [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) модуль не знает, в какой сборке он находится, и получение идентификатора родительской сборки невозможно. `ModuleAttachedToAssembly`Метод вызывается, когда модуль присоединяется к своей родительской сборке и может быть ПОЛУЧЕН идентификатор его родительской сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
