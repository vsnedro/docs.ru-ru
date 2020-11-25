---
title: Интерфейс ICorDebugValue3
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 419efc7f21f4ac2e68657b2a4d69a8690a2938d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722314"
---
# <a name="icordebugvalue3-interface"></a>Интерфейс ICorDebugValue3

Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, размер которых превышает 2 ГБ.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetSize64](icordebugvalue3-getsize64-method.md)|Возвращает размер данного объекта в байтах `ICorDebugValue3` .|  
  
## <a name="remarks"></a>Комментарии  

 Метод [ICorDebugValue::](icordebugvalue3-getsize64-method.md) GetBytes возвращает размер объекта в диапазоне от 0 до 2 147 483 647 байт. В .NET Framework 4,5 размер массивов может превышать 2 ГБ. `ICorDebugValue3`Интерфейс позволяет определить размер этих массивов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
