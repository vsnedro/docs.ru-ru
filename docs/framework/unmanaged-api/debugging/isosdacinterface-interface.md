---
description: 'Дополнительные сведения о: интерфейс ИсосдаЦинтерфаце'
title: Интерфейс ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ddb99b7c6fca6870024f04933861d01e4b31ea9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790403"
---
# <a name="isosdacinterface-interface"></a>Интерфейс ISOSDacInterface

Предоставляет вспомогательные методы для доступа к данным из `SOS` .

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                               | Описание                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](isosdacinterface-getmethoddescdata-method.md) | Возвращает данные для заданного указателя MethodDesc. |
| [GetMethodDescPtrFromIP](isosdacinterface-getmethoddescptrfromip-method.md) | Получает указатель MethodDesc, соответствующий методу, содержащему указанный адрес собственной инструкции. |
| [GetModuleData](isosdacinterface-getmoduledata-method.md)| Извлекает данные, соответствующие модулю, загруженному по указанному адресу. |

## <a name="remarks"></a>Remarks

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , который можно получить с помощью стандартных механизмов com.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
