---
description: 'Дополнительные сведения о методе: Икордебугхеапсегментенум:: Next'
title: Метод ICorDebugHeapSegmentEnum::Next
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 8d2ddfb4df82969fa9cf580ed8a7f903f9d6c260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803680"
---
# <a name="icordebugheapsegmentenumnext-method"></a>Метод ICorDebugHeapSegmentEnum::Next

Возвращает указанное число экземпляров [COR_SEGMENT](cor-segment-structure.md) , содержащих сведения о регионах памяти управляемой кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 celt  
 окне Число извлекаемых сегментов.  
  
 сегменты  
 заполняет Массив указателей, каждый из которых указывает на объект [COR_SEGMENT](cor-segment-structure.md) , который предоставляет сведения о области памяти в управляемой куче.  
  
 pceltFetched  
 заполняет Указатель на число объектов [COR_SEGMENT](cor-segment-structure.md) , фактически возвращаемых в `segments` . Это значение может быть `null`, если параметр `celt` имеет значение 1.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
