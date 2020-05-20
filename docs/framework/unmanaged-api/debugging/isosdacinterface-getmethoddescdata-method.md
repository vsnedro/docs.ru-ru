---
title: 'Метод ИсосдаЦинтерфаце:: Жетмесоддескдата'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421024"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Метод ИсосдаЦинтерфаце:: Жетмесоддескдата

Возвращает данные для заданного указателя MethodDesc.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a>Параметры

`methodDesc`\
окне Адрес MethodDesc.

`ip`\
окне IP-адрес метода.

`data`\
заполняет Данные, связанные с MethodDesc, возвращаются из внутренних API-интерфейсов.

`cRevertedRejitVersions`\
заполняет Число восстановленных версий rejit.

`rgRevertedRejitData`\
заполняет Данные, связанные с возвращенными версиями rejit, возвращенные из внутренних API.

`pcNeededRevertedRejitData`\
заполняет Число байтов, необходимое для хранения данных, связанных с возвращенными версиями ReJit.

## <a name="remarks"></a>Комментарии

Предоставленный метод является частью `ISOSDacInterface` интерфейса и соответствует 21-сегменту таблицы виртуального метода. Чтобы иметь возможность использовать их, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) необходимо определить как 64-разрядное целое число без знака.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также статью

- [Отладка](index.md)
- [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)
