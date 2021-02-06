---
description: 'Дополнительные сведения: структура COR_PRF_EX_CLAUSE_INFO'
title: Структура COR_PRF_EX_CLAUSE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: af8d404e55a8996abc69923924e87c95e3c5eae8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649212"
---
# <a name="cor_prf_ex_clause_info-structure"></a>Структура COR_PRF_EX_CLAUSE_INFO

Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`clauseType`|Значение перечисления [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) , указывающее тип предложения исключения, введенного или левого кода.|  
|`programCounter`|Собственная точка входа обработчика предложения, например, содержимое регистра x86 EIP.|  
|`framePointer`|Указатель на логический кадр для обработчика предложения, например содержимое регистра x86 EBP.|  
|`shadowStackPointer`|Указатель на теневой стек. Это значение является содержимым регистра BSP и применяется только к версии IA64.|  
  
## <a name="remarks"></a>Remarks  

 При получении уведомления об исключении можно использовать [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) для получения сведений о собственном адресе и кадре для предложения исключения ( `catch` / `finally` /Filter), которое должно быть запущено или только что было запущено.  
  
 Выполнение предложения исключения включает следующие обратные вызовы из среды CLR:  
  
- [ICorProfilerCallback:: Ексцептионкатчерентер](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионунвиндфиналлентер](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионсеарчфилтерентер](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионкатчерлеаве](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [ICorProfilerCallback:: Exceptionunwindfinallyleave-](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [ICorProfilerCallback:: Ексцептионсеарчфилтерлеаве](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры профилирования](profiling-structures.md)
