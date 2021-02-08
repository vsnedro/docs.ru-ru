---
description: 'Дополнительные сведения о методе: Икорпрофилерфунктионконтрол:: Сетилинструментедкодемап'
title: Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
ms.openlocfilehash: bb345f737459342e0146cbb0e0bd7dd4b1e9a037
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781549"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a>Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap

Устанавливает карту кода для указанной функции с помощью указанных записей карты языка CIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cILMapEntries`  
 [в] Количество записей в карте.  
  
 `rgILMapEntries`  
 [в] Массив записей COR_IL_MAP, выделенный вызывающим объектом. Интерпретация этих записей такая же, как и для метода [ICorProfilerInfo:: сетилинструментедкодемап](icorprofilerinfo-setilinstrumentedcodemap-method.md) .  
  
## <a name="remarks"></a>Remarks  

 Установка сопоставления путем вызова этого метода позволяет отладчику получить сопоставление путем вызова [ICorDebugILCode2:: GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md). Кроме того, он позволяет отладчику использовать сопоставление внутренним образом при вычислении смещений промежуточного языка для трассировок стека и времени существования переменных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
