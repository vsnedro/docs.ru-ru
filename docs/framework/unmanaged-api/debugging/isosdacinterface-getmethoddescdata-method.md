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
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396949"
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

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `ISOSDacInterface` интерфейса и соответствует 21-сегменту таблицы виртуального метода. Чтобы иметь возможность использовать их, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) необходимо определить как 64-разрядное целое число без знака.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также статью

- [Отладка](index.md)
- [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)
