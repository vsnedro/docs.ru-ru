---
description: 'Дополнительные сведения о методе: ICorProfilerObjectEnum:: Skip'
title: Метод ICorProfilerObjectEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 8a2aa5dd2b905931b97fafa4db6709aab16aacc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781263"
---
# <a name="icorprofilerobjectenumskip-method"></a>Метод ICorProfilerObjectEnum::Skip

Перемещает курсор этого перечислителя из текущей позиции, чтобы было пропущено указанное число элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 окне Число пропущенных элементов.  
  
## <a name="remarks"></a>Remarks  

 Новая позиции курсора перечислителя: (Текущая позиции) + `celt` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)
