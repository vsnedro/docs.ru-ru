---
title: Метод ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: ccbb051ac30fb25199ce12c16fff74bb0b9944fa
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495090"
---
# <a name="icorprofilermoduleenumclone-method"></a>Метод ICorProfilerModuleEnum::Clone
Получает указатель интерфейса на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) . Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя. Однако начальная позиции курсора копии совпадает с текущей позицией курсора этого перечислителя.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
