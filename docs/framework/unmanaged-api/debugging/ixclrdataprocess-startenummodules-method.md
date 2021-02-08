---
description: 'Дополнительные сведения о методе: Иксклрдатапроцесс:: Стартенуммодулес'
title: 'Метод Иксклрдатапроцесс:: Стартенуммодулес'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2e90c646ee8815ec10ce0bbd7538f13d7b5dcf8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800588"
---
# <a name="ixclrdataprocessstartenummodules-method"></a>Метод Иксклрдатапроцесс:: Стартенуммодулес

Предоставляет описатель для перечисления модулей процесса.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Параметры

`handle`\
заполняет Маркер для перечисления модулей.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует слоту 24 таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
