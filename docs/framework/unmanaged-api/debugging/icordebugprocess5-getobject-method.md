---
title: Метод ICorDebugProcess5::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: ff2913399e1dbeb33bbfb697058db3caf2a8d1fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713110"
---
# <a name="icordebugprocess5getobject-method"></a>Метод ICorDebugProcess5::GetObject

Преобразует адрес объекта в объект "ICorDebugObjectValue".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `addr`  
 окне Адрес объекта.  
  
 `ppObject`  
 заполняет Указатель на адрес объекта "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Комментарии  

 Если не `addr` указывает на допустимый управляемый объект, `GetObject` метод возвращает значение `E_FAIL` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
