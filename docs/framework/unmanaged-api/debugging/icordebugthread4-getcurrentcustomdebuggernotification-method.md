---
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
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378699"
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

**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugThread4](icordebugthread4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
