---
description: Дополнительные сведения о методе Message. Бодитостринг
title: Метод Message. Бодитостринг (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: babcd881d191ff46b98e9999c4ff04166479a68d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699380"
---
# <a name="messagebodytostring-method"></a>Метод Message. Бодитостринг

Преобразует текст сообщения в строку путем вызова <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> метода.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Параметры

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Модуль записи, используемый для преобразования тела сообщения в строку.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `Message.BodyToString`Метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.ServiceModel.Channels>

**Сборка:** System.ServiceModel.dll

**Платформа .NET Framework версии:** Доступно с 3,0.
