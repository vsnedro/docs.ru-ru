---
title: Структура DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a65fa9974165fa36e59a7fb83dca6dd902f7d8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724399"
---
# <a name="dacpgetmoduleaddress-structure"></a>Структура DacpGetModuleAddress

Определяет контейнер для запроса адреса модуля.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>Члены

| Член      | Описание                |
| ----------- | -------------------------- |
| `ModulePtr` | Указатель на модуль. |

## <a name="methods"></a>Методы

| Метод                                                                                               | Описание                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Запрос](dacpgetmoduleaddress-request-method.md) | Выполняет запрос на заполнение структуры из заданной структуры среды выполнения. |

## <a name="remarks"></a>Комментарии

Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Чтобы использовать его, определите структуру, как указано выше, где `CLRDATA_ADDRESS` — это 64-разрядное целое число без знака.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Отладка](index.md)
- [Структуры отладки](debugging-structures.md)
