---
description: 'Дополнительные сведения о методе: ИсосдаЦинтерфаце:: Жетмодуледата'
title: 'Метод ИсосдаЦинтерфаце:: Жетмодуледата'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c01f55d55d5ee9082dee4b3adb3022bb17807aa2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790390"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>Метод ИсосдаЦинтерфаце:: Жетмодуледата

Извлекает данные, соответствующие модулю, загруженному по указанному адресу.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>Параметры

`moduleAddr`\
окне Адрес модуля, для которого нужно получить сведения.

`data`\
заполняет [Структура дакпмодуледата](dacpmoduledata-structure.md) для хранения сведений о загруженном модуле.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `ISOSDacInterface` интерфейса и соответствует слоту 14 таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)
