---
description: Дополнительные сведения <section> element
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 7756f7ee3be2391a0d068708f3719083640b5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639943"
---
# <a name="section-element"></a>Элемент \<section>

Содержит объявление раздела конфигурации.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a>Синтаксис

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Требуемые атрибуты

|           | Описание |
| --------- | ----------- |
| **name**  | Задает имя раздела конфигурации. |
| **type**  | Указывает имя класса обработчика раздела конфигурации, считывающего раздел из файла конфигурации. Значение типа имеет синтаксис "полное имя-раздела-класса-обработчика", простое-Assembly-Name ". В качестве простого имени сборки используется имя корневого файла без расширения *DLL* . |

## <a name="optional-attributes"></a>Необязательные атрибуты

Следующие атрибуты применимы только для приложений ASP.NET. Система конфигурации пропускает эти атрибуты для других типов приложений.

|                     | Описание |
| ------------------- | ----------- |
| **allowDefinition** | Указывает файл конфигурации, в котором может использоваться раздел. Используйте одно из следующих значений:<br><br>**Везде**<br>Позволяет использовать раздел в любом файле конфигурации. Это значение по умолчанию.<br>**MachineOnly**<br>Позволяет использовать раздел только в файле конфигурации компьютера (*Machine.config*).<br>**MachineToApplication**<br>Позволяет использовать раздел в файле конфигурации компьютера или файле конфигурации приложения. |
| **allowLocation**   | Определяет, можно ли использовать раздел в **\<location>** элементе. Используйте одно из следующих значений:<br><br>**true**<br>Позволяет использовать раздел внутри **\<location>** элемента. Это значение по умолчанию.<br>**false**<br>Не позволяет использовать раздел внутри **\<location>** элемента. |

## <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [**\<configSections>** Элемент](configsections-element-for-configuration.md) | Содержит раздел конфигурации и объявления пространств имен. |
| [**\<sectionGroup>** Дерев](sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |

> [!NOTE]
> **\<section>** Элемент — это дочерний элемент либо, либо, **\<configSections>** **\<sectionGroup>** но не оба.

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

Объявление раздела конфигурации фактически определяет новый элемент для файла конфигурации. Новый элемент содержит параметры, которые обработчик раздела конфигурации (то есть класс, реализующий <xref:System.Configuration.IConfigurationSectionHandler> интерфейс) считывает. Атрибуты и дочерние элементы определяемого раздела зависят от обработчика раздела, используемого для чтения параметров.

Объявление обработчика раздела конфигурации в файле *Machine.config* позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если в атрибуте **allowDefinition** не указано иное.

## <a name="example"></a>Пример

В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
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
