---
description: 'Дополнительные сведения о: <remove> Element для <appSettings>'
title: Элемент <remove> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: a67003d310377ee4b896843003306201353dae91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699276"
---
# <a name="remove-element-for-appsettings"></a>Элемент \<remove> для \<appSettings>

Удаляет пользовательские параметры приложения.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>attribute

|         | Описание |
| ------- | ----------- |
| **key** | Обязательный атрибут.<br><br>Задает имя удаляемого ключа. |

### <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="example"></a>Пример

В следующем примере показано, как удалить настраиваемый параметр конфигурации для `ApplicationName` :

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](../index.md)
