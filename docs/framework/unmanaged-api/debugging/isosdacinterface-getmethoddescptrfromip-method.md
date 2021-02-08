---
description: 'Дополнительные сведения о методе: ИсосдаЦинтерфаце:: Жетмесоддескптрфромип'
title: 'Метод ИсосдаЦинтерфаце:: Жетмесоддескптрфромип'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 8d7c7071b7b3fc520faea71c8d7792317745cfde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790416"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>Метод ИсосдаЦинтерфаце:: Жетмесоддескптрфромип

Получает указатель MethodDesc, соответствующий методу, содержащему указанный адрес собственной инструкции.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a>Параметры

`ip`\
окне Адрес в методе во время выполнения.

`ppMD`\
заполняет Адрес `MethodDesc` для конкретного метода.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью [ `ISOSDacInterface` интерфейса](isosdacinterface-interface.md) и соответствует слоту 22 таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)
