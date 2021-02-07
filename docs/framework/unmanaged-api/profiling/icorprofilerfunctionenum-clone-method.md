---
description: 'Дополнительные сведения о методе: ICorProfilerFunctionEnum:: Clone'
title: Метод ICorProfilerFunctionEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: 6cadadd98f64a27de0cd4e7d264fe797d22c33a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737679"
---
# <a name="icorprofilerfunctionenumclone-method"></a>Метод ICorProfilerFunctionEnum::Clone

Получает указатель интерфейса на копию этого интерфейса [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppEnum`  
 заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) . Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя. Однако начальная позиции курсора копии совпадает с текущей позицией курсора этого перечислителя.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
