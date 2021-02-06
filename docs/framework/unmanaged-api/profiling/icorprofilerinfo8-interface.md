---
description: 'Дополнительные сведения о: интерфейс ICorProfilerInfo8'
title: Интерфейс ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4538c9d314283c67ab0bfe6af3f3768062cffda4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646547"
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
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
