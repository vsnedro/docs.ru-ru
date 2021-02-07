---
description: 'Дополнительные сведения о методе: ICorDebugProcess4::P Роцессстатечанжед'
title: 'ICorDebugProcess4: метод:P Роцессстатечанжед'
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 35a76b3c6dd9b37d3f06f23bc2ffea82f125a29e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746477"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4: метод:P Роцессстатечанжед

Уведомляет конвейер ICorDebug о том, что отладчик out-Process продолжает выполнение отлаживаемого кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Параметры

 `eChange`\
окне Член [перечисления кордебугстатечанже](cordebugstatechange-enumeration.md) , описывающий изменение в состоянии выполнения процесса.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `ICorDebugProcess4` интерфейса и соответствует четвертому слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** None

 **Библиотека:** None

 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
