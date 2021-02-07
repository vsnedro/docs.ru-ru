---
description: 'Дополнительные сведения о: <configuration> element'
title: <configuration> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: ee48a45ddb987201e84213a0d7674da004951ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699002"
---
# <a name="configuration-element"></a>Элемент \<configuration>

Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Синтаксис

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Атрибуты

None

## <a name="parent-element"></a>Родительский элемент

None

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | Определяет политику привязки сборок на уровне конфигурации.|
| [**\<startup>** Схема параметров](./startup/index.md) | Все элементы в схеме параметров запуска. |
| [**\<runtime>** Схема параметров](./runtime/index.md) | Все элементы в схеме параметров среды выполнения. |
| [**\<system.runtime.remoting>** Схема параметров](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Все элементы в схеме параметров удаленного взаимодействия. |
| [**\<system.Net>** Схема параметров](./network/index.md) | Все элементы в схеме параметров сети. |
| [**\<cryptographySettings>** Схема параметров](./cryptography/index.md) | Все элементы в схеме параметров шифрования. |
| [**\<configuration>** Схема разделов](configuration-sections-schema.md) | Все элементы в схеме параметров раздела конфигурации. |
| [Схема параметров трассировки и отладки](./trace-debug/index.md) | Все элементы в схеме параметров трассировки и отладки. |
| [Схема параметров конфигурации ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Все элементы в схеме конфигурации ASP.NET, включая элементы для настройки веб-сайтов и приложений ASP.NET. Используется в файлах *Web.config* . |
| [**\<webServices>** Схема параметров](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Все элементы в схеме параметров веб-служб. |
| [Схема веб-параметров](./web/index.md) | Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS. Используется в файлах *aspnet.config* . |

## <a name="remarks"></a>Remarks

Каждый файл конфигурации должен содержать ровно один **\<configuration>** элемент.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](index.md)
