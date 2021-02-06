---
description: Дополнительные сведения о методе Енумимпорттипес
title: Метод EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: 39570740f3560f5bfef8ba80b95c0eb2aca41f59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638123"
---
# <a name="enumimporttypes-method"></a>Метод EnumImportTypes

Перечисляет каждый тип в каждой области.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>Параметры

`hEnum`\
Обработчик для перечислителя.

`dwMax`\
Максимальное число извлекаемых типов.

`aTypeDefs`\
Получает токены типа, не превышающие их `dwMax` .

`pdwCount`\
Получает фактическое число типа в `aTypeDefs` .

## <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если метод завершается с ошибкой.

## <a name="requirements"></a>Требования

Требуется ALink. h

## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
