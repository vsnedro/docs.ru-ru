---
title: Метод ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 9f5688ae4f76f9ddfde231aa6252d666c9152eec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731087"
---
# <a name="icordebugvaluegetsize-method"></a>Метод ICorDebugValue::GetSize

Возвращает размер этого объекта "ICorDebugValue" в байтах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pSize`  
 заполняет Размер данного объекта значения в байтах.  
  
## <a name="remarks"></a>Комментарии  

 Если типом значения является ссылочный тип, этот метод возвращает размер указателя, а не размер объекта.  
  
 `ICorDebugValue::GetSize`Метод возвращает `COR_E_OVERFLOW` для объектов, размер которых ПРЕВЫШАЕТ 4 гб на 64-разрядных платформах. Используйте вместо него метод [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) для объектов, размер которых ПРЕВЫШАЕТ 4 ГБ.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetSize64](icordebugvalue3-getsize64-method.md)
