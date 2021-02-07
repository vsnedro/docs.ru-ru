---
description: 'Дополнительные сведения о методе ICorProfilerInfo:: ForceGC'
title: Метод ICorProfilerInfo::ForceGC
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: 1abed09450b72730a11a168223b6da05e9baf9be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737536"
---
# <a name="icorprofilerinfoforcegc-method"></a>Метод ICorProfilerInfo::ForceGC

Принудительное выполнение сборки мусора в среде CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Remarks  

 `ForceGC`Метод должен вызываться только из потока, который никогда не выполнял управляемый код и не имеет обратных вызовов профилировщика в стеке. Наиболее удобной реализацией является создание отдельного потока в профилировщике, который вызывает `ForceGC` при получении сигнала.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
