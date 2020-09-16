---
title: Перечисление COR_PRF_REJIT_FLAGS
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 1b1d6ad5d465d746f4c1a9400c43613591373322
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546950"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>Перечисление COR_PRF_REJIT_FLAGS
Содержит значения, указывающие поведение API [ICorProfilerInfo10:: рекуестрежитвисинлинерс](icorprofilerinfo10-requestrejitwithinliners-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| Методы Режиттед будут заблокированы из встроенных в другие методы. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| Получение `GetFunctionParameters` обратных вызовов для всех методов, которые подставляемые методы режиттед. |  

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](profiling-enumerations.md)
