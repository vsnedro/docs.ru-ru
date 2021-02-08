---
description: 'Дополнительные сведения о: структура Дакпрежитдата'
title: Структура DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 8e8d506856dbc6579ac6ea0eee2b2088a980a315
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801440"
---
# <a name="dacprejitdata-structure"></a>Структура DacpReJitData

Определяет основные сведения о конкретном инструментированном методе профилирования.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a>Члены

| Член           | Описание                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | Номер редакции ReJit для метода.                                                          |
| `flags`          | Флаг, указывающий текущее состояние инструментирования ReJit метода для данной версии. |
| `NativeCodeAddr` | Базовый адрес реализации режиттед метода.                                         |

## <a name="remarks"></a>Remarks

Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Чтобы использовать его, определите структуру, как указано выше. Структура также должна быть определена с помощью `ms_struct` упаковки, если не используется компиляторы Майкрософт.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Структуры отладки](debugging-structures.md)
