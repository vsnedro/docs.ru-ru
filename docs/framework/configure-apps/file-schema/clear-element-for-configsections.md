---
title: Элемент <clear> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155431"
---
# <a name="clear-element-for-configsections"></a>Элемент \<clear> для \<configSections>

Удаляет все ранее определенные разделы и группы разделов.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Синтаксис

```xml
<clear/>
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

**\<clear>** Элемент удаляет все разделы и группы разделов из приложения, которые были определены ранее в текущем файле конфигурации или на более высоком уровне иерархии файлов конфигурации.

## <a name="example"></a>Пример

В этом примере определяется файл конфигурации компьютера и файл конфигурации приложения, а также демонстрируется использование **\<clear>** элемента в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации компьютера.

В следующем коде файла конфигурации компьютера объявляются два раздела **\<sampleSection>** и **\<anotherSampleSection>** , которые считываются перед файлом конфигурации приложения:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

В следующем коде файла конфигурации приложения очищаются все ранее объявленные разделы. Приложение не может использовать или извлекать параметры в одном из разделов, объявленных в файле конфигурации компьютера. Однако он может использовать параметры из, **\<anotherSection>** так как он находится после **\<clear>** элемента.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
