---
description: 'Дополнительные сведения: схема параметров приложения'
title: Схема параметров приложения
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a98a60b0470e0fa2c03313f25de9b310f5fce785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699354"
---
# <a name="app-settings-schema"></a>Схема параметров приложения

Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| Элемент | Описание |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Содержит **\<add>** **\<clear>** теги, и **\<remove>** для управления параметрами приложения. Имеет необязательный атрибут **file**. |
| [**\<add>**](add-element-for-appsettings.md) | Определяет параметр. Дочерний элемент **\<appSettings>** . Обязательные атрибуты — **key** и **value**. |
| [**\<clear>**](clear-element-for-appsettings.md) | Удаляет все параметры. Дочерний элемент **\<appSettings>** . Не имеет атрибутов. |
| [**\<remove>**](remove-element-for-appsettings.md) | Удаляет параметр. Дочерний элемент **\<appSettings>** . Требуется атрибут **key**. |

## <a name="appsettings-element"></a>Элемент \<appSettings>

Этот элемент содержит **\<add>** **\<clear>** теги, и **\<remove>** для управления параметрами приложения. Определяет необязательный атрибут для **file**.

## <a name="add-element"></a>Элемент \<add>

Добавляет пользовательский параметр приложения в виде пары "имя-значение" в коллекцию параметров приложения. Определяет атрибуты для **key** и **value**.

## <a name="clear-element"></a>Элемент \<clear>

Удаляет все ссылки на унаследованные пользовательские параметры приложения и разрешает только ссылки, добавленные **\<add>** элементами после **\<clear>** элемента. Атрибуты не определяются.

## <a name="remove-element"></a>Элемент \<remove>

Удаляет ссылку на унаследованный пользовательский параметр приложения из коллекции параметров приложения. Определяет атрибут для **key**.

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

## <a name="see-also"></a>См. также

- [Общие сведения о параметрах приложений](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [Архитектура параметров приложения](/dotnet/desktop/winforms/advanced/application-settings-architecture)
