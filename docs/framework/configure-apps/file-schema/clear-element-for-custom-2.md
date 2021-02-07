---
description: 'Дополнительные сведения о: <clear> Element для NameValueSectionHandler и DictionarySectionHandler'
title: <clear> элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: 896aa7e8f0e3b41574538fcd9e4be9d6155da889
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699237"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<clear> элемент для NameValueSectionHandler и DictionarySectionHandler

Удаляет все ранее определенные параметры в разделе.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Синтаксис

```xml
<clear />
```

## <a name="attributes"></a>Атрибуты

None

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ------------|
| [**\<sectionName>** Элемент](custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, использующих <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> классы и. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

С помощью элемента можно **\<clear>** удалить из приложения все параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В этом примере определяется файл конфигурации компьютера и файл конфигурации приложения, а также демонстрируется использование **\<clear>** элемента в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации компьютера.

Следующий код файла конфигурации компьютера объявляет раздел **\<mySection>** :

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

Следующий код файла конфигурации приложения удаляет все параметры из **\<mySection>** . Приложение не может получить параметры, которые были объявлены в в **\<mySection>** разделе файла конфигурации компьютера.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*) и *Web.config* файлах, которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](index.md)
