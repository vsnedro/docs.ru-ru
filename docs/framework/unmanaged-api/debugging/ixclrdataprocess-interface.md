---
description: 'Дополнительные сведения о: интерфейс Иксклрдатапроцесс'
title: Интерфейс IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b611491e5c9a5957c07a305a3f395b67ad208649
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800647"
---
# <a name="ixclrdataprocess-interface"></a>Интерфейс IXCLRDataProcess

Предоставляет методы для запроса сведений о процессе.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                                               | Описание                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetRuntimeNameByAddress](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | Возвращает имя для заданного адреса.                                                               |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Возвращает `AppDomain` в процессе по его уникальному идентификатору.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Предоставляет описатель для перечисления модулей процесса.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Перечисляет модули этого процесса.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении модулей.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Предоставляет описатель для перечисления экземпляров методов, `AppDomain` начиная с заданного адреса. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.             |

## <a name="remarks"></a>Remarks

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , который можно получить с помощью стандартных механизмов com.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
