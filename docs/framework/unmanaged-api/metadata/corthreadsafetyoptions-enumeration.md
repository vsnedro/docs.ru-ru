---
description: Дополнительные сведения о перечислении CorThreadSafetyOptions
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
ms.openlocfilehash: 7915bcf5e7b71fa84ea83642467c1600cd38712d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707323"
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

## <a name="members"></a>Члены

|Член|Описание|
|------------|-----------------|
|`MDThreadSafetyDefault`|Значение по умолчанию. Эквивалентно `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Указывает, что невозможно установить блокировку потоков чтения/записи.|
|`MDThreadSafetyOn`|Указывает, что можно задать блокировку потоков чтения/записи.|

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** Корхдр. h

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
