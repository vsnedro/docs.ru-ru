---
description: 'Дополнительные сведения о методе: ICorProfilerModuleEnum:: Skip'
title: Метод ICorProfilerModuleEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
ms.openlocfilehash: 4d814e5e9e369fe286b471fadc9675345cfb5b94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798970"
---
# <a name="icorprofilermoduleenumskip-method"></a>Метод ICorProfilerModuleEnum::Skip

Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 окне Число пропущенных элементов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`celt` элементы пропущены.|  
|S_FALSE|`celt`Пропущено меньше элементов, что означает, что больше нет элементов.|  
  
## <a name="remarks"></a>Remarks  

 Новая позиции курсора перечислителя — (Текущая позиции) + `celt` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
