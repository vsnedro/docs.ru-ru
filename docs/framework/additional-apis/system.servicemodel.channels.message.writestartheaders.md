---
description: Дополнительные сведения о методе Message. Вритестарсеадерс
title: Метод Message. Вритестарсеадерс (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 20cadf5f1eecf6d8e02c5dc4597889abaef4ec36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699367"
---
# <a name="messagewritestartheaders-method"></a>Метод Message. Вритестарсеадерс

Записывает начальный заголовок в XML-файл, вызвав <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> метод.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Параметры

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Модуль записи, используемый для записи начального заголовка в XML-файл.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `Message.WriteStartHeaders`Метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.ServiceModel.Channels>

**Сборка:** System.ServiceModel.dll

**Платформа .NET Framework версии:** Доступно с 3,0.
