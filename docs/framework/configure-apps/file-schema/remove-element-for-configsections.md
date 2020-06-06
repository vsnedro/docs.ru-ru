---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154534"
---
# <a name="remove-element-for-configsections"></a>Элемент \<remove> для \<configSections>

Удаляет предопределенный раздел или группу разделов.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Синтаксис

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **name**  | Обязательный атрибут.<br><br>Указывает имя раздела или группы разделов, которые нужно удалить. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<configSections>** Дерев](configsections-element-for-configuration.md) | Содержит раздел конфигурации и объявления пространств имен. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

Элемент можно использовать **\<remove>** для удаления разделов и групп разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В следующем примере показано, как использовать **\<remove>** элемент в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации компьютера.

Следующий код файла конфигурации компьютера объявляет раздел **\<sampleSection>** :

```xml
<!-- Machine.config file -->
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

Следующий код файла конфигурации приложения удаляет **\<sampleSection>** раздел. После удаления приложение не сможет получить параметры в **\<sampleSection>** .

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
