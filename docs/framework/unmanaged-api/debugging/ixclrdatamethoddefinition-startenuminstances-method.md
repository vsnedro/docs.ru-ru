---
description: 'Дополнительные сведения о методе: Иксклрдатамесоддефинитион:: Стартенуминстанцес'
title: 'Метод Иксклрдатамесоддефинитион:: Стартенуминстанцес'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 74de6360c90766cfec17e6b88a495fe2a70858b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800829"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>Метод Иксклрдатамесоддефинитион:: Стартенуминстанцес

Предоставляет обработчик для перечисления экземпляров методов для заданного объекта `IXCLRDataAppDomain` .

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Параметры

`appDomain`\
окне Домен приложения для перечисления.

`handle`\
заполняет Маркер для перечисления экземпляров.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует 5-сегменту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
