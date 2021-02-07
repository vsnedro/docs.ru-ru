---
description: 'Дополнительные сведения о: <assemblyBinding> Element для <configuration>'
title: Элемент <assemblyBinding> для <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 5cc3fc7cccd4b9dc7b62815734ff76e32e2243d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730113"
---
# <a name="assemblybinding-element-for-configuration"></a>Элемент \<assemblyBinding> для \<configuration>

Определяет политику привязки сборок на уровне конфигурации.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Синтаксис

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>attribute

|           | Описание |
| --------- | ----------- |
| **xmlns** | Обязательный атрибут.<br><br>Задает пространство имен XML, необходимое для привязки сборок. Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-element"></a>Дочерний элемент

|     | Описание |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | Указание файла конфигурации, который следует включить. |

## <a name="remarks"></a>Remarks

[**\<linkedConfiguration>**](linkedconfiguration-element.md)Элемент упрощает управление сборками компонентов, позволяя файлам конфигурации приложения включать файлы конфигурации сборки в хорошо известные расположения, а не дублировать параметры конфигурации сборки.

> [!NOTE]
> **\<linkedConfiguration>** Элемент не поддерживается для приложений с параллельными манифестами Windows.

## <a name="example"></a>Пример

В следующем примере показано, как включить файл конфигурации на локальный жесткий диск:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для платформа .NET Framework](index.md)
