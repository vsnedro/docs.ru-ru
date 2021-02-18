---
title: Свойства MSBuild для Microsoft.NET.Sdk.Desktop
description: Справочник по свойствам и элементам MSBuild, распознаваемым пакетом SDK для классических приложений .NET, который включает WPF и WinForms.
ms.date: 02/04/2021
ms.topic: reference
author: adegeo
ms.author: adegeo
ms.custom: updateeachrelease
no-loc:
- App.xaml
- Application.xaml
- ApplicationDefinition
- Page
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: 6d1903558dd03776a72eb6ee56ddae09fb66615b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488271"
---
# <a name="msbuild-reference-for-net-desktop-sdk-projects"></a>Справочник по MSBuild для проектов пакета SDK для классических приложений .NET

На этой странице приведена ссылка на свойства и элементы MSBuild, используемые для настройки проектов Windows Forms (WinForms) и Windows Presentation Foundation (WPF) с помощью пакета SDK для классических приложений .NET.

> [!NOTE]
> В этой статье приведено подмножество свойств MSBuild для пакета SDK для .NET, поскольку он связан с классическими приложениями. Список полезных свойств для проектов .NET см. в статье [Справочник по MSBuild для проектов пакета SDK для .NET](msbuild-props.md). Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="enable-net-desktop-sdk"></a>Включение пакета SDK для классических приложений .NET

Чтобы использовать WinForms или WPF, настройте файл проекта.

### <a name="net-50"></a>.NET 5.0

Укажите следующие параметры в файле проекта для WinForms или проекта WPF:

- Выполните нацеливание для `Microsoft.NET.Sdk` пакета SDK для .NET. Дополнительные сведения см. в разделе [Файлы проекта](overview.md#project-files).
- Присвойте параметру [`TargetFramework`](msbuild-props.md#targetframework) значение `net5.0-windows`.
- При необходимости добавьте свойство платформы пользовательского интерфейса (или и то, и другое):
  - Присвойте параметру [`UseWPF`](#usewpf) значение `true`, чтобы импортировать и использовать WPF.
  - Присвойте параметру [`UseWindowsForms`](#usewindowsforms) значение `true`, чтобы импортировать и использовать WinForms.
- (Необязательно) Присвойте параметру `OutputType` значение `WinExe`. При этом создается приложение, а не библиотека. Чтобы создать библиотеку, опустите это свойство.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

### <a name="net-core-31"></a>.NET Core 3.1

Укажите следующие параметры в файле проекта для WinForms или проекта WPF:

- Выполните нацеливание для `Microsoft.NET.Sdk.WindowsDesktop` пакета SDK для .NET. Дополнительные сведения см. в разделе [Файлы проекта](overview.md#project-files).
- Присвойте параметру [`TargetFramework`](msbuild-props.md#targetframework) значение `netcoreapp3.1`.
- При необходимости добавьте свойство платформы пользовательского интерфейса (или и то, и другое):
  - Присвойте параметру [`UseWPF`](#usewpf) значение `true`, чтобы импортировать и использовать WPF.
  - Присвойте параметру [`UseWindowsForms`](#usewindowsforms) значение `true`, чтобы импортировать и использовать WinForms.
- (Необязательно) Присвойте параметру `OutputType` значение `WinExe`. При этом создается приложение, а не библиотека. Чтобы создать библиотеку, опустите это свойство.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

## <a name="wpf-default-includes-and-excludes"></a>Включения и исключения WPF по умолчанию

Проекты SDK определяют набор правил для неявного включения или исключения файлов из проекта. Эти правила также автоматически устанавливают действие сборки файла. Это отличается от старых проектов .NET Framework, не использующих пакет SDK, которые не имеют правил включения или исключения по умолчанию. В проектах .NET Framework требуется явное объявление того, какие файлы следует включить в проект.

Файлы проектов .NET включают [стандартный набор правил](overview.md#default-includes-and-excludes) для автоматической обработки файлов. Проекты WPF добавляют дополнительные правила.

В следующей таблице показано, какие элементы и [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены в пакет SDK для классических приложений .NET и исключены из него, когда свойству проекта [`UseWPF`](#usewpf) задано значение `true`:

| Элемент               | Стандартная маска включения                 | Стандартная маска исключения                                                                                           | Стандартная маска удаления  |
|-----------------------|------------------------------|--------------------------------------------------------------------|--------------|
| ApplicationDefinition | App.xaml или Application.xaml | Н/Д                                                                | Н/Д          |
| Page                  | \*\*/\*.xaml                 | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc<br>Любой XAML, определенный *ApplicationDefinition* | Н/Д          |
| None                  | Н/Д                          | Н/Д                                                                | \*\*/\*.xaml |

Ниже приведены параметры включения и исключения по умолчанию для всех типов проектов. Дополнительные сведения см. в разделе [Включения и исключения по умолчанию](overview.md#default-includes-and-excludes).

| Элемент           | Стандартная маска включения                              | Стандартная маска исключения                                                  | Стандартная маска удаления              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs; \*\*/\*.vb (или другие расширения языка) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | Н/Д          |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Н/Д                      |
| None              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

### <a name="errors-related-to-duplicate-items"></a>Ошибки, связанные с повторяющимися элементами

Если вы явно добавили файлы в проект или используете стандартные маски XAML для автоматического включения файлов в проект, может возникать одна из следующих ошибок:

* Включены дублирующиеся элементы "ApplicationDefinition".
* Включены дублирующиеся элементы "Page".

Эти ошибки являются результатом неявного *включения* стандартных масок, конфликтующих с вашими настройками. Чтобы обойти эту проблему, задайте параметру [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) или [`EnableDefaultPageItems`](#enabledefaultpageitems) значение `false`. При установке этих значений в `false` возвращается поведение предыдущих пакетов SDK, где необходимо явно определить стандартные маски по умолчанию в проекте или явно определить файлы для включения в проект.

Все неявные включения можно полностью отключить, установив для свойства [`EnableDefaultItems` ](msbuild-props.md#enabledefaultitems)значение `false`.

## <a name="wpf-settings"></a>Параметры WPF

- [UseWPF](#usewpf)
- [EnableDefaultApplicationDefinition](#enabledefaultapplicationdefinition)
- [EnableDefaultPageItems](#enabledefaultpageitems)

Дополнительные сведения о параметрах проектов, отличных от WPF, см. в разделе [Справочник по MSBuild для проектов пакета SDK для .NET](msbuild-props.md).

### <a name="usewpf"></a>UseWPF

Свойство `UseWPF` определяет, следует ли включать ссылки на библиотеки WPF. Это также приводит к соответствующему изменению конвейера MSBuild для правильной обработки проекта WPF и связанных файлов. Значение по умолчанию — `false`. Задайте для свойства `UseWPF` значение `true`, чтобы включить поддержку WPF. Выполнить нацеливание на платформу Windows можно только в том случае, если это свойство включено.

```xml
<PropertyGroup>
  <UseWPF>true</UseWPF>
</PropertyGroup>
```

Если это свойство имеет значение `true`, проекты .NET 5.0+ автоматически импортируют [пакет SDK для классических приложений .NET](#enable-net-desktop-sdk).

Для использования этого свойства проекты .NET Core 3.1 должны быть явно предназначены для [пакета SDK для классических приложений.NET](#enable-net-desktop-sdk).

### <a name="enabledefaultapplicationdefinition"></a>EnableDefaultApplicationDefinition

Свойство `EnableDefaultApplicationDefinition` определяет, включаются ли в проект неявным образом элементы `ApplicationDefinition`. Значение по умолчанию — `true`. Задайте значение `false` для свойства `EnableDefaultApplicationDefinition`, чтобы отключить неявные включения файлов.

```xml
<PropertyGroup>
  <EnableDefaultApplicationDefinition>false</EnableDefaultApplicationDefinition>
</PropertyGroup>
```

Для этого свойства необходимо, чтобы свойство [`EnableDefaultItems` ](msbuild-props.md#enabledefaultitems) имело значение `true`, которое является значением по умолчанию.

### <a name="enabledefaultpageitems"></a>EnableDefaultPageItems

Свойство `EnableDefaultPageItems` определяет, включаются ли в проект неявным образом элементы `Page`, которые являются файлами _.xaml_. Значение по умолчанию — `true`. Задайте значение `false` для свойства `EnableDefaultPageItems`, чтобы отключить неявные включения файлов.

```xml
<PropertyGroup>
  <EnableDefaultPageItems>false</EnableDefaultPageItems>
</PropertyGroup>
```

Для этого свойства необходимо, чтобы свойство [`EnableDefaultItems` ](msbuild-props.md#enabledefaultitems) имело значение `true`, которое является значением по умолчанию.

## <a name="windows-forms-settings"></a>Параметры Windows Forms

- [UseWindowsForms](#usewindowsforms)

Дополнительные сведения о свойствах проектов, отличных от WinForms, см. в разделе [Справочник по MSBuild для проектов пакета SDK для .NET](msbuild-props.md).

### <a name="usewindowsforms"></a>UseWindowsForms

Свойство `UseWindowsForms` определяет, предназначено ли приложение для Windows Forms. Это свойство изменяет конвейер MSBuild соответствующим образом для правильной обработки Windows Forms проекта и связанных файлов. Значение по умолчанию — `false`. Задайте для свойства `UseWindowsForms` значение `true`, чтобы включить поддержку Windows Forms. Выполнить нацеливание на платформу Windows можно только в том случае, если этот параметр включен.

```xml
<PropertyGroup>
  <UseWindowsForms>true</UseWindowsForms>
</PropertyGroup>
```

Если это свойство имеет значение `true`, проекты .NET 5.0+ автоматически импортируют [пакет SDK для классических приложений .NET](#enable-net-desktop-sdk).

Для использования этого свойства проекты .NET Core 3.1 должны быть явно предназначены для [пакета SDK для классических приложений.NET](#enable-net-desktop-sdk).

## <a name="shared-settings"></a>Общие параметры

- [DisableWinExeOutputInference](#disablewinexeoutputinference)

### <a name="disablewinexeoutputinference"></a>DisableWinExeOutputInference

Применимо к пакету SDK для .NET 5.0 и более поздних версий.

Если в приложении свойству `OutputType` присвоено значение `Exe`, создается окно консоли, если приложение не запускается из консоли. Обычно это не является необходимым поведением классического приложения Windows. Если присвоено значение `WinExe`, окно консоли не создается. Начиная с пакета SDK для .NET 5.0, значение `Exe` автоматически преобразуется в `WinExe`.

Свойство `DisableWinExeOutputInference` возвращает поведение при обработке `Exe` как `WinExe`. Присвойте этому параметру значение `true`, чтобы восстановить поведение значения свойства `OutputType` для `Exe`. Значение по умолчанию — `false`.

```xml
<PropertyGroup>
  <DisableWinExeOutputInference>true</DisableWinExeOutputInference>
</PropertyGroup>
```

## <a name="see-also"></a>См. также

- [Пакеты SDK для проектов .NET](overview.md)
- [Справочник по MSBuild для проектов пакета SDK для .NET](msbuild-props.md)
- [Справочник по схеме MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties)
- [Настройка сборки](/visualstudio/msbuild/customize-your-build)
