---
description: 'Дополнительные сведения: структура COR_PRF_GC_GENERATION_RANGE'
title: Структура COR_PRF_GC_GENERATION_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: ea67a6e6b972b9406b84ad331e8af6189327c5ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648926"
---
# <a name="cor_prf_gc_generation_range-structure"></a>Структура COR_PRF_GC_GENERATION_RANGE

Описывает диапазон (т. е., блок) памяти, который занимается сборкой мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`generation`|Значение перечисления [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , указывающее поколение, к которому принадлежит блок памяти.|  
|`rangeStart`|Идентификатор объекта, указывающего начальное расположение блока памяти.|  
|`rangeLength`|Указатель на целое число, задающее размер используемой части блока памяти (то есть объема памяти, используемого в блоке).|  
|`rangeLengthReserved`|Указатель на целое число, задающее размер блока памяти (то есть объема памяти, зарезервированного для блока).|  
  
## <a name="remarks"></a>Remarks  

 `rangeLength`Значение гарантированно будет точным только в том случае, если [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) или [ICorProfilerInfo2:: GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), обе из которых используют `COR_PRF_GC_GENERATION_RANGE` структуру, вызывается из метода [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) или [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры профилирования](profiling-structures.md)
