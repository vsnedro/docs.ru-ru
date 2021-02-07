---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: Комклассиквтабледестройед'
title: Метод ICorProfilerCallback::COMClassicVTableDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
ms.openlocfilehash: 91ed5bb65d3a64f1f85a09a710b507974f51c79b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706387"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a>Метод ICorProfilerCallback::COMClassicVTableDestroyed

Уведомляет профилировщик о том, что виртуальная таблица COM-взаимодействия удалена.  
  
> [!NOTE]
> Этот обратный вызов, скорее всего, никогда не происходит, так как уничтожение vtable происходит очень близко к завершению работы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a>Параметры

- `wrappedClassId`

  \[in] идентификатор класса, для которого была создана эта таблица vtable.

- `implementedIID`

  \[in] идентификатор интерфейса, реализуемого классом. Это значение может быть равно NULL, если интерфейс является только внутренним.

- `pVTable`

  \[in] указатель на начало таблицы vtable.

## <a name="remarks"></a>Remarks  

 Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора. Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.  
  
 Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод COMClassicVTableCreated](icorprofilercallback-comclassicvtablecreated-method.md)
