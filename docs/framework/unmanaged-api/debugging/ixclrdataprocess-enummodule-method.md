---
description: 'Дополнительные сведения о методе: Иксклрдатапроцесс:: Енуммодуле'
title: 'Метод Иксклрдатапроцесс:: Енуммодуле'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 33b15da6939a0fb78a4eeafcf75e1a2b2f0d0ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800686"
---
# <a name="ixclrdataprocessenummodule-method"></a>Метод Иксклрдатапроцесс:: Енуммодуле

Перечисляет модули этого процесса.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a>Параметры

`handle`\
[вход, выход] Маркер для перечисления модулей.

`mod`\
заполняет Перечисленный модуль.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует 25-е слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
