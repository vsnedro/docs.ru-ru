---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 1e4bb7a7cfb0b140ca6d13c162708c3c30bd496d
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441691"
---
# <a name="configsections-element-for-configuration"></a>Элемент \<configSections> для \<configuration>

Содержит раздел конфигурации и объявления пространств имен.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**

## <a name="attributes"></a>Атрибуты

Нет

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<section>**](section-element.md) | Содержит объявление раздела конфигурации. |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |

## <a name="remarks"></a>Комментарии

Если этот элемент находится в файле конфигурации, он должен быть первым дочерним элементом **\<configuration>** элемента.

## <a name="example"></a>Пример

В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.

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

## <a name="see-also"></a>Дополнительно

- [Схема файла конфигурации для .NET Framework](index.md)
