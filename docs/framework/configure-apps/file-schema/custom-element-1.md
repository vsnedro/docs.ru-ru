---
description: 'Дополнительные сведения о: настраиваемый элемент для Синглетагсектионхандлер'
title: Настраиваемый элемент для Синглетагсектионхандлер
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 83022a1ebf295b89d5f868589e3d9a77c78e3fab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729983"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Настраиваемый элемент для Синглетагсектионхандлер

Определяет параметры в пользовательском разделе конфигурации, определяемом \<section> элементом, и использует <xref:System.Configuration.SingleTagSectionHandler> класс.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*

## <a name="syntax"></a>Синтаксис

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>Атрибуты

Атрибуты и значения атрибутов определяются пользователем.

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

**\<sectionName>** Элемент является пользовательским элементом, определяемым [**\<section>**](section-element.md) тегом в [**\<configSections>**](configsections-element-for-configuration.md) элементе. Система конфигурации возвращает <xref:System.Collections.IDictionary> объект при вызове метода <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .

## <a name="example"></a>Пример

В следующем примере объявляется пользовательский элемент с именем **\<sampleSection>** , который содержит параметры, считанные <xref:System.Configuration.SingleTagSectionHandler> классом:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*) и *Web.config* файлах, которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](index.md)
