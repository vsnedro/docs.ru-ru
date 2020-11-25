---
title: Перечисление COR_PRF_SNAPSHOT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 5290db008bfe5727ed5899c2ed6f7e41ae9a353a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716360"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>Перечисление COR_PRF_SNAPSHOT_INFO

Указывает объем данных, которые необходимо передать обратно с помощью моментального снимка стека при каждом вызове функции [стаккснапшоткаллбакк](stacksnapshotcallback-function.md) профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Элементы|Описание|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, кроме `context` параметра.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, включая `context` параметр.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Указывает, что будет использоваться более простой и альтернативный алгоритм анализа стека.|  
  
## <a name="remarks"></a>Комментарии  

 Значения, предоставляемые `COR_PRF_SNAPSHOT_INFO` перечислением, передаются в качестве параметров в метод [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Перечисления профилирования](profiling-enumerations.md)
