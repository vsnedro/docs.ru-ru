---
description: 'Дополнительные сведения о: <add> Element для <appSettings>'
title: Элемент <add> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: f10ffe517b3b25543bc7baed0c7d2af13f48ab02
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652891"
---
# <a name="add-element-for-appsettings"></a>Элемент \<add> для \<appSettings>

Добавляет пользовательский параметр приложения.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a>Атрибуты

|           | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Указывает имя добавляемого ключа. |
| **value** | Обязательный атрибут.<br><br>Указывает значение добавляемого ключа. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="example"></a>Пример

В следующем примере показано, как добавить настраиваемый параметр конфигурации для имени приложения:

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

В следующем примере элемент используется `<add>` для определения двух параметров совместимости в приложении ASP.NET:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](../index.md)
