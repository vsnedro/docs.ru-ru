---
description: 'Дополнительные сведения о: <appSettings> Element для <configuration>'
title: Элемент <appSettings> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 74a25bb0dffd97057cda45575745b6f51ad2a675
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802493"
---
# <a name="appsettings-element-for-configuration"></a>Элемент \<appSettings> для \<configuration>

Содержит пользовательские параметры приложения. Это предварительно определенный раздел конфигурации, предоставляемый платформа .NET Framework.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>attribute

|           | Описание |
| --------- | ----------- |
| **file**  | Необязательный атрибут.<br><br>Указывает относительный путь к внешнему файлу, содержащему настраиваемые параметры конфигурации приложения. Указанный файл содержит те же параметры, что указаны в **\<add>** **\<remove>** элементах, и, **\<clear>** и использует тот же формат пар "ключ-значение", что и эти элементы.<br><br>Путь указан относительно основного файла конфигурации. Для Windows Forms приложения это двоичная папка (например, */бин/дебуг*), а не расположение файла конфигурации приложения. Для приложений веб-форм путь определяется относительно корневого каталога приложения, где расположен файл *web.config* .<br><br>Среда выполнения игнорирует атрибут, если не удается найти указанный файл. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<configuration>** Элемент](../configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | Добавляет пользовательский параметр приложения. |
| [**\<clear>**](clear-element-for-appsettings.md) | Удаляет все ранее определенные параметры приложения. |
| [**\<remove>**](remove-element-for-appsettings.md) | Удаляет ранее определенный параметр приложения. |

## <a name="remarks"></a>Remarks

**\<appSettings>** Элемент хранит сведения о конфигурации пользовательского приложения, такие как строки подключения к базе данных, пути к файлам, URL-адреса XML или другие пользовательские сведения о конфигурации приложения. Пары "ключ-значение", указанные в **\<appSettings>** элементе, доступны в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.

Атрибут **File** можно использовать в **\<appSettings>** элементе *Web.config* и файлах конфигурации приложения. Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяющий параметры, указанные в **\<appSettings>** элементе. Атрибут **File** может использоваться в сценариях разработки группы управления исходным кодом, например, когда пользователь хочет переопределить параметры проекта, указанные в файле конфигурации приложения.

Файлы конфигурации, заданные атрибутом **File** , должны иметь корневой узел, **\<appSettings>** а не **\<configuration>** .

## <a name="example"></a>Пример

В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*) и *Web.config* файлах, которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](../index.md)
