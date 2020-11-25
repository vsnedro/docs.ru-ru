---
title: Структура DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: dcf01c00a106c131646a16597dca4092a06c5983
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723068"
---
# <a name="dacpmethoddescdata-structure"></a>Структура DacpMethodDescData

Определяет транспортный буфер для сведений о среде выполнения метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a>Члены

| Член                       | Описание                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Указывает, доступен ли в среде выполнения машинный код для данного экземпляра метода. |
| `bIsDynamic`                 | Указывает, создается ли метод динамически с помощью создания упрощенного кода.           |
| `wSlotNumber`                | Номер слота метода в таблице методов.                                                   |
| `NativeCodeAddr`             | Начальный собственный адрес метода.                                                            |
| `data`                       | Указатель на буфер, который используется средой выполнения для внутренних целей.                                             |
| `MethodDescPtr`              | Указатель на объект `MethodDesc` в среде выполнения.                                                     |
| `nativeCodeInfo`             | Указатель на буфер, используемый средой выполнения для трассировки методов.                            |
| `moduleInfo`                 | Указатель на буфер, используемый средой выполнения для сведений о модуле.                      |
| `MDToken`                    | Токен, связанный с данным методом.                                                         |
| `payloadGC`                  | Указатель на буфер сборки мусора, который используется средой выполнения для внутренних целей.                          |
| `payloadGC2`                 | Указатель на буфер сборки мусора, который используется средой выполнения для внутренних целей.                          |
| `managedDynamicMethodObject` | Если метод является динамическим, среда выполнения использует этот буфер для внутреннего отслеживания сведений.     |
| `requestedIP`                | Используется для заполнения структуры на запрос при наличии адреса машинного кода.                    |
| `rejitDataCurrent`           | Сведения о последней инструментированной версии метода.                                   |
| `rejitDataRequested`         | Rejit сведения для запрошенного собственного адреса.                                             |
| `cJittedRejitVersions`       | Сколько раз метод был режиттед с помощью инструментирования.                           |

## <a name="remarks"></a>Комментарии

Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Чтобы использовать его, определите структуру, как указано выше.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Отладка](index.md)
- [Структуры отладки](debugging-structures.md)
- [Общие типы данных](../common-data-types-unmanaged-api-reference.md)
