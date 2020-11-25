---
title: Метод ICorProfilerInfo2::EnumModuleFrozenObjects
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: fe4f3a7355339c9b5adbe5de062f0a5688d81c23
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727189"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a>Метод ICorProfilerInfo2::EnumModuleFrozenObjects

Возвращает перечислитель, позволяющий выполнять итерацию зафиксированных объектов в указанном модуле. Этот метод устарел.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleID`  
 окне Идентификатор модуля, содержащего зафиксированные объекты для перечисления.  
  
 `ppEnum`  
 заполняет Указатель на адрес интерфейса [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , который перечисляет зафиксированные объекты.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
