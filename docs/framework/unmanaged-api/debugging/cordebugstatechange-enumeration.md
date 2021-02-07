---
description: Дополнительные сведения о перечислении Кордебугстатечанже
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
ms.openlocfilehash: 1900baa77432daa10d0f1a32dd9cb25198b86ed1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661822"
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

## <a name="members"></a>Члены

| Член            | Описание                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.            |
| `FLUSH_ALL`       | Память процесса может отличаться произвольным образом от предыдущего варианта. |

## <a name="remarks"></a>Remarks

 Член `CorDebugStateChange` перечисления предоставляется в качестве аргумента, когда отладчик вызывает `ProcessStateChanged` метод с помощью [ICorDebugProcess4::P роцессстатечанжед](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6::P роцессстатечанжед](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** CorDebug.idl, CorDebug.h

 **Библиотека:** CorGuids.lib

 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
