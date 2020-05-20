---
title: 'Метод Иксклрдатамесодинстанце:: Жетрепресентативинтряддресс'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d546cda5c68732e75550a3de286089f7df261c91
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420907"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>Метод Иксклрдатамесодинстанце:: Жетрепресентативинтряддресс

Возвращает наиболее репрезентативный адрес точки входа для собственной компиляции всех возможных точек входа для метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Параметры

`addr`\
заполняет Адрес наиболее репрезентативной собственной точки входа для метода.

## <a name="remarks"></a>Комментарии

Предоставленный метод является частью [ `IXCLRDataMethodInstance` интерфейса](ixclrdatamethodinstance-interface.md) и соответствует слоту 20 таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также статью

- [Отладка](index.md)
- [Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
