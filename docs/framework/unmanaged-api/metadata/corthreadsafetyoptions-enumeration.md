---
title: Перечисление CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007511"
---
# <a name="corthreadsafetyoptions-enumeration"></a>Перечисление CorThreadSafetyOptions

Задает флаги для выбора параметров безопасности потока.

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>Участники

|Член|Описание|
|------------|-----------------|
|`MDThreadSafetyDefault`|Значение по умолчанию. Эквивалентно `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Указывает, что невозможно установить блокировку потоков чтения/записи.|
|`MDThreadSafetyOn`|Указывает, что можно задать блокировку потоков чтения/записи.|

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** Корхдр. h

**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
