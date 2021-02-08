---
description: 'Дополнительные сведения о методе: Иксклрдатапроцесс:: Стартенуммесодинстанцесбяддресс'
title: 'Метод Иксклрдатапроцесс:: Стартенуммесодинстанцесбяддресс'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 155d09192b60b8671435abb439f07dfbb290bc87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800595"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a>Метод Иксклрдатапроцесс:: Стартенуммесодинстанцесбяддресс

Предоставляет описатель для перечисления экземпляров методов, `AppDomain` начиная с заданного адреса.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a>Параметры

`address`\
окне Адрес первого экземпляра метода.

`appDomain`\
окне AppDomain экземпляров метода.

`handle`\
заполняет Описатель для перечисления экземпляров методов.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28-го слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
