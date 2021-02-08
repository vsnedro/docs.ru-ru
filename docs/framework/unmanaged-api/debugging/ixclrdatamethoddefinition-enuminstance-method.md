---
description: 'Дополнительные сведения о методе: Иксклрдатамесоддефинитион:: Енуминстанце'
title: 'Метод Иксклрдатамесоддефинитион:: Енуминстанце'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4038dc4706b8362acaf9c13abd9c7326cce376a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790364"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>Метод Иксклрдатамесоддефинитион:: Енуминстанце

Перечисляет экземпляры этого определения метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a>Параметры

`handle`\
[вход, выход] Маркер для перечисления экземпляров.

`instance`\
заполняет Перечислимый экземпляр.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует шестому слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
- [Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
