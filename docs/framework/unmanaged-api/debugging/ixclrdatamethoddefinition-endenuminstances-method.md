---
description: 'Дополнительные сведения о методе: Иксклрдатамесоддефинитион:: Енденуминстанцес'
title: 'Метод Иксклрдатамесоддефинитион:: Енденуминстанцес'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: bfdcb9046b4983e6686410bf2ceadf7119b89e74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790377"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>Метод Иксклрдатамесоддефинитион:: Енденуминстанцес

Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Параметры

`handle`\
заполняет Маркер для перечисления экземпляров.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует седьмому слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
