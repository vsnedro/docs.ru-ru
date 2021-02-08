---
description: 'Дополнительные сведения о: интерфейс Иксклрдатамодуле'
title: Интерфейс IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 403d4dd3db64f2855347562da7217a3562985c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800751"
---
# <a name="ixclrdatamodule-interface"></a>Интерфейс IXCLRDataModule

Предоставляет методы для запроса сведений о загруженном модуле.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                                | Описание                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Возвращает определение метода, соответствующее заданному маркеру метаданных. |
| [Запрос](ixclrdatamodule-request-method.md)                                       | Запросы на заполнение буфера данными модуля.       |
| [GetVersionId](ixclrdatamodule-getversionid-method.md)                             | Возвращает идентификатор версии модуля.                                       |

## <a name="remarks"></a>Remarks

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , который можно получить с помощью стандартных механизмов com.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
