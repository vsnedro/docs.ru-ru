---
description: 'Дополнительные сведения о: интерфейс Иксклрдатамесоддефинитион'
title: Интерфейс IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d73246b42a0bfb982c87b04d5490e945f7caa745
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790351"
---
# <a name="ixclrdatamethoddefinition-interface"></a>Интерфейс IXCLRDataMethodDefinition

Предоставляет методы для запроса сведений об определении метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

Ниже перечислены методы, доступные в интерфейсе.

| Метод                                                                                                                          | Описание                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](ixclrdatamethoddefinition-startenuminstances-method.md) | Предоставляет обработчик для перечисления экземпляров методов для заданного объекта `IXCLRDataAppDomain` . |
| [EnumInstance](ixclrdatamethoddefinition-enuminstance-method.md)             | Перечисляет экземпляры этого определения метода.                                         |
| [EnumInstance](ixclrdatamethoddefinition-endenuminstances-method.md)     | Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.         |

## <a name="remarks"></a>Remarks

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` , который можно получить с помощью стандартных механизмов com.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
