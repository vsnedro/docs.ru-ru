---
title: Интерфейс ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f38195b1a7983e23c7f5c20055ea8c2a8bfcb7d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556854"
---
# <a name="icorprofilerinfo9-interface"></a>Интерфейс ICorProfilerInfo9

Подкласс [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , предоставляющий методы для запроса сведений о функциях с несколькими версиями машинного кода.  

## <a name="methods"></a>Методы  

| Метод|Описание|  
| ------------|-----------------|  
|[Метод GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md)| При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют. |
|[Метод GetILToNativeMapping3](icorprofilerinfo9-getiltonativemapping3-method.md)| С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода. |
|[Метод GetCodeInfo4](icorprofilerinfo9-getcodeinfo4-method.md)| При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код. |

## <a name="requirements"></a>Требования  
**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).  
**Заголовок:** CorProf.idl, CorProf.h  
**Версии .NET:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
