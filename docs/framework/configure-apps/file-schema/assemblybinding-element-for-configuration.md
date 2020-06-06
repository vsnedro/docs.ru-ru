---
title: Элемент <assemblyBinding> для <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155483"
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

## <a name="attribute"></a>Атрибут

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

## <a name="remarks"></a>Примечания

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

- [Схема файла конфигурации для .NET Framework](index.md)
