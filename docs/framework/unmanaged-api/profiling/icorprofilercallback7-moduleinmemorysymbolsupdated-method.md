---
description: 'Дополнительные сведения о методе: ICorProfilerCallback7:: Модулеинмеморисимболсупдатед'
title: 'Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: 74adf7edc5269824a924933eb3284a5964e1bac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781731"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед

[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Уведомляет профилировщик каждый раз, когда поток символов, связанный с модулем в памяти, обновляется.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>Параметры  

 [in] `moduleId`  
 Идентификатор модуля в памяти, чей поток символов обновлен.  
  
## <a name="remarks"></a>Remarks  

 Этот обратный вызов управляется путем установки флага [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) маски событий при вызове метода [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> Это событие в данный момент не вызывается для неявного создания или изменения символов через <xref:System.Reflection.Emit> API-интерфейсы.  
  
 Даже если символы предоставляются перед вызовом одной из перегрузок управляемых <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> методов, включающих `rawSymbolStore` аргумент для указания символов для сборки, среда выполнения может фактически не связывать символьные данные с модулем до тех пор, пока не будет вызван обратный вызов [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) . Это событие предоставляет более позднюю возможность собираются символы для таких модулей.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
- [Метод SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)
- [Интерфейс ICorProfilerCallback7](icorprofilercallback7-interface.md)
