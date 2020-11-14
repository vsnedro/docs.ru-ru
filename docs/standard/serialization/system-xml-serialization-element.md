---
title: Элемент <system.xml.serialization>
description: В статье описан <system.xml.serialization> — элемент верхнего уровня для управления сериализацией XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 6291799aadc429e943996f2256d773ac36dd370f
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282387"
---
# <a name="systemxmlserialization-element"></a>Элемент \<system.xml.serialization>

Элемент верхнего уровня для управления XML-сериализацией. Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md).

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a>Синтаксис

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<dateTimeSerialization> Элемент](datetimeserialization-element.md)|Определяет режим сериализации объектов <xref:System.DateTime>.|
|[\<schemaImporterExtensions> Элемент](schemaimporterextensions-element.md)|Содержит типы, которые <xref:System.Xml.Serialization.XmlSchemaImporter> использует для сопоставления типов XSD с типами .NET.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<configuration> Элемент](../../framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.|

## <a name="example"></a>Пример

В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET.

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a>См. также

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md)
- [\<dateTimeSerialization> Элемент](datetimeserialization-element.md)
- [\<schemaImporterExtensions> Элемент](schemaimporterextensions-element.md)
- [Элемент \<add> для \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
