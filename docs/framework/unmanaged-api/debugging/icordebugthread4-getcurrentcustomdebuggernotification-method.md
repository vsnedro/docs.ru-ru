---
description: 'Дополнительные сведения о методе: ICorDebugThread4:: GetCurrentCustomDebuggerNotification'
title: Метод ICorDebugThread4::GetCurrentCustomDebuggerNotification
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: 20d9449e98b9ab91dbdec84ba026e91514d5b3cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800946"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a>Метод ICorDebugThread4::GetCurrentCustomDebuggerNotification

Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a>Параметры

`ppNotificationObject`\
заполняет Указатель на текущий `ICorDebugManagedCallback3::CustomNotification` объект в текущем потоке.

## <a name="remarks"></a>Remarks

Значение `ppNotificationObject` равно null, если метод не вызывается из `ICorDebugManagedCallback3::CustomNotification` обратного вызова или если текущий объект уведомления не существует.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugThread4](icordebugthread4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
