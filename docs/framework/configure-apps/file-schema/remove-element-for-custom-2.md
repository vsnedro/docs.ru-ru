---
title: <remove>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214759"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<remove>элемент для NameValueSectionHandler и DictionarySectionHandler

Удаляет ранее определенный параметр.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Синтаксис

```xml
<add remove="key" />
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Задает имя удаляемого параметра. |

## <a name="parent-element"></a>Родительский элемент

| Элемент | Описание |
| ------- | ------------|
| [**\<sectionName>** Дерев](custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, использующих <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> классы и. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

С помощью элемента можно **\<remove>** удалить из приложения параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В следующем примере показано, как использовать **\<remove>** элемент в файле конфигурации приложения для удаления параметров, ранее определенных в файле конфигурации компьютера.

Следующий код файла конфигурации компьютера объявляет раздел **\<mySection>** и добавляет `key1` `key2` в него два параметра:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Следующий код файла конфигурации приложения удаляет `key2` параметр из **\<mySection>** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
