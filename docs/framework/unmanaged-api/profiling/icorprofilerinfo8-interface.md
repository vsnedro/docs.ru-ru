---
title: Интерфейс ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: eedd16006781de517587e5138543b9b9eca3ff90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733611"
---
# <a name="icorprofilerinfo8-interface"></a>Интерфейс ICorProfilerInfo8

Подкласс [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , предоставляющий методы для запроса сведений о динамических методах.

## <a name="methods"></a>Методы  

| Метод|Описание|  
| ------------|-----------------|  
|[Метод IsFunctionDynamic](icorprofilerinfo8-isfunctiondynamic-method.md)| Определяет, имеет ли функция связанные метаданные.|
|[Метод GetFunctionFromIP3](icorprofilerinfo8-getfunctionfromip3-method.md)| Сопоставляет указатель инструкции управляемого кода с FunctionID. Этот метод работает как с динамическими, так и с нединамическими методами. |
|[Метод GetDynamicFunctionInfo](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Извлекает сведения о динамических методах. |

## <a name="requirements"></a>Требования  

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** CorProf.idl, CorProf.h  
**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
