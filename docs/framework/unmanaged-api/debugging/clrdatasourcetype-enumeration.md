---
description: Дополнительные сведения о перечислении Клрдатасаурцетипе
title: Перечисление Клрдатасаурцетипе
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 06590e21aa4cdf6e89977a79da36a413d5ff4f1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747246"
---
# <a name="clrdatasourcetype-enumeration"></a>Перечисление Клрдатасаурцетипе

Предоставляет значения, используемые структурой CLRDATA_IL_ADDRESS_MAP.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a>Члены

| Член                        | Описание                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | Указание того, что ничего еще не применимо |

## <a name="remarks"></a>Remarks

Это перечисление находится внутри среды выполнения и не предоставляется через заголовки или файлы библиотек. Чтобы использовать его, определите перечисление, как определено выше в коде. Это также называется псевдонимом, `CLRDATA_ENUM` как упоминалось в [общих типах данных](../common-data-types-unmanaged-api-reference.md).

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Перечисления отладки](debugging-enumerations.md)
