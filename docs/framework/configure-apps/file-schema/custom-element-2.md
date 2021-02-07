---
description: 'Дополнительные сведения о: настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler'
title: Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: c1bb5b2fb321e2cc9235e02be2158c0875d42032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698730"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler

Определяет параметры для пользовательских разделов конфигурации, использующих <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> классы и.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a>Атрибуты

None

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<add>**](add-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>  | Добавляет настраиваемые параметры приложения. |
| [**\<remove>**](remove-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> | Удаляет ранее определенный параметр. |
| [**\<clear>**](clear-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> | Удаляет все ранее определенные параметры в разделе. |

## <a name="remarks"></a>Remarks

**\<sectionName>** Элемент является пользовательским элементом, определяемым **\<section>** тегом в **\<configSections>** элементе.

В следующей таблице показан тип объекта, возвращаемого методом ConfigurationSettings. config для каждого обработчика раздела конфигурации:

| Обработчик раздела конфигурации                        | Возвращаемый тип                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Пример

В следующем примере показано, как объявить разделы, в которых используются <xref:System.Configuration.DictionarySectionHandler> <xref:System.Configuration.NameValueSectionHandler> классы и.

Первый настраиваемый элемент — **\<dictionarySample>** , который содержит параметры, считанные <xref:System.Configuration.DictionarySectionHandler> классом в `System.dll` сборке. Второй настраиваемый элемент — **\<mySection>** , который содержит параметры, считанные <xref:System.Configuration.NameValueSectionHandler> классом в `System.dll` сборке.

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*) и *Web.config* файлах, которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](index.md)
