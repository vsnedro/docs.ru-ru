---
description: 'Дополнительные сведения о методе: Иксклрдатамодуле:: Жетверсионид'
title: 'Метод Иксклрдатамодуле:: Жетверсионид'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1b924757f43d106df555ea028270ac873f8f4558
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800764"
---
# <a name="ixclrdatamodulegetversionid-method"></a>Метод Иксклрдатамодуле:: Жетверсионид

Возвращает идентификатор версии модуля.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a>Параметры

`vid`\
заполняет Идентификатор версии модуля.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту й таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)
