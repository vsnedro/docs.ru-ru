---
description: 'Дополнительные сведения о: <clear> Element для <appSettings>'
title: Элемент <clear> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 88c6a02441c038619cb74947c024de7712189915
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699341"
---
# <a name="clear-element-for-appsettings"></a>Элемент \<clear> для \<appSettings>

Удаляет пользовательские параметры приложения.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Атрибуты

None

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML или другие сведения о конфигурации пользовательских приложений. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="example"></a>Пример

В следующем примере показано, как удалить настраиваемые параметры конфигурации.

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](../index.md)
