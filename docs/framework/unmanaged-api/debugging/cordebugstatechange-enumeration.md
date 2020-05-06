---
title: Перечисление CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: d94422d25da91cd2a6653a95cbd852c3930a151a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795694"
---
# <a name="cordebugstatechange-enumeration"></a>Перечисление CorDebugStateChange

Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Участники

| Участник            | Описание                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.            |
| `FLUSH_ALL`       | Память процесса может отличаться произвольным образом от предыдущего варианта. |

## <a name="remarks"></a>Remarks

 Член `CorDebugStateChange` перечисления предоставляется в качестве аргумента, когда отладчик вызывает `ProcessStateChanged` метод с помощью [ICorDebugProcess4::P Роцессстатечанжед](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6::P роцессстатечанжед](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** CorDebug.idl, CorDebug.h

 **Библиотека:** CorGuids.lib

 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также раздел

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
