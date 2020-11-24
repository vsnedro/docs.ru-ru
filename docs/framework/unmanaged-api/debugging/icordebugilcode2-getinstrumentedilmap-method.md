---
title: Метод ICorDebugILCode2::GetInstrumentedILMap
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 097502f4321531922d6c4385e2eccbf32f66f026
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688358"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>Метод ICorDebugILCode2::GetInstrumentedILMap

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 cMap  
 [в] Емкость хранилища массива `map`. Дополнительные сведения см. в разделе "Примечания".  
  
 pcMap  
 [из] Количество значений COR_IL_MAP, записанных в массив сопоставлений.  
  
 карта  
 [из] Массив значений COR_IL_MAP, предоставляющий информацию о сопоставлениях промежуточного языка, инструментированного профилировщиком, и промежуточного языка исходного метода.  
  
## <a name="remarks"></a>Комментарии  

 Если профилировщик задает сопоставление путем вызова метода [ICorProfilerInfo:: сетилинструментедкодемап](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , отладчик может вызвать этот метод, чтобы получить сопоставление и использовать внутреннее сопоставление при вычислении смещений Il для трассировок стека и времени существования переменных.  
  
 Если значение `cMap` равно 0 и `pcMap` не равно **null**, то параметру присваивается `pcMap` число доступных COR_IL_MAP значений. Если значение `cMap` не равно 0, оно обозначает емкость хранилища массива `map`. Когда метод возвращает значение, `map` содержит максимум `cMap` элементов и `pcMap` задается числом COR_IL_MAP значений, фактически записанных в `map` массив.  
  
 Если промежуточный язык не инструментирован или профилировщик не предоставил сопоставление, этот метод возвращает значение `S_OK` и присваивает `pcMap` значение 0.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
