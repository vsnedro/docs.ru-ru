---
title: Перечисление COR_PRF_GC_ROOT_KIND
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: 0ea584bfff4340e5e9635d6c31e177e88765b582
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500875"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a>Перечисление COR_PRF_GC_ROOT_KIND
Указывает тип корневого элемента сборки мусора, предоставляемый обратным вызовом [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|Корень — это переменная в стеке.|  
|`COR_PRF_GC_ROOT_FINALIZER`|Корень — это запись в очереди метода завершения.|  
|`COR_PRF_GC_ROOT_HANDLE`|Корень является обработчиком сборки мусора.|  
|`COR_PRF_GC_ROOT_OTHER`|Тип корня не указан.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](profiling-enumerations.md)
