---
description: 'Дополнительные сведения о: интерфейс Иксклрдатамесодинстанце'
title: Интерфейс IXCLRDataMethodInstance
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4e9ad57988420ff14b297c693c31c0dc5b3b181c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800790"
---
# <a name="ixclrdatamethodinstance-interface"></a>Интерфейс IXCLRDataMethodInstance

Предоставляет методы для запроса сведений об экземпляре метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                  | Описание                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [GetILAddressMap](ixclrdatamethodinstance-getiladdressmap-method.md) | Возвращает IL для сопоставления сведений о сопоставлении. |
| [GetRepresentativeEntryAddress](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | Возвращает наиболее репрезентативный адрес точки входа для собственной компиляции всех возможных точек входа для метода. |

## <a name="remarks"></a>Remarks

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , который можно получить с помощью стандартных механизмов com.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
