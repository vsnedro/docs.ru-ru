---
title: Элемент <add> для <schemaImporterExtensions>
description: Элемент <add> добавляет типы, используемые классом XmlSchemaImporter для сопоставления типов XSD с типами .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 6fd8113ad39a22c927035fca574151ae8f002685
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288333"
---
# <a name="add-element-for-schemaimporterextensions"></a>Элемент \<add> для \<schemaImporterExtensions>
Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter>, для сопоставления типов XSD с типами платформы .NET Framework. Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md).  
  
 \<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**name**|Простое имя, используемое для поиска экземпляра.|  
|**type**|Обязательный. Задает добавляемый класс расширения схемы. Значение атрибута **type** должно располагаться на одной строке и содержать полное имя типа. Когда сборка помещается в глобальный кэш сборок (GAC), она должна также содержать версию, язык и региональные параметры и маркер открытого ключа подписанной сборки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|Содержит типы, используемые классом<xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере кода добавляется тип расширения, который XmlSchemaImporter может использовать при сопоставлении типов.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [\<system.xml.serialization> Элемент](system-xml-serialization-element.md)
- [\<schemaImporterExtensions> Элемент](schemaimporterextensions-element.md)
