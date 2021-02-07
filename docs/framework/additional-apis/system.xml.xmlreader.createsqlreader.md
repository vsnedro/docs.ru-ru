---
description: Дополнительные сведения о методе XmlReader. Креатесклреадер
title: Метод XmlReader. Креатесклреадер (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 61d594c0438c86863ce4052387439f5483d8a34c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740438"
---
# <a name="xmlreadercreatesqlreader-method"></a>Метод XmlReader.CreateSqlReader

Создает новый экземпляр <xref:System.Xml.XmlReader>, используя заданный поток, параметры и контекстную информацию для анализа.

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>Параметры

- `input` <xref:System.IO.Stream>  
  Поток, содержащий XML-данные.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  Параметры нового экземпляра <xref:System.Xml.XmlReader>. Это значение может быть равно `null`.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  Для синтаксического анализа фрагмента XML необходимы контекстные сведения. Это значение может быть равно `null`.

## <a name="returns"></a>Возвращаемое значение

<xref:System.Xml.XmlReader>  
Объект, используемый для чтения данных XML в потоке.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `XmlReader.CreateSqlReader`Метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Xml>

**Сборка:** System.Xml.dll

**Платформа .NET Framework версии:** Доступно с 2,0.
