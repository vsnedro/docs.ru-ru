---
title: Критическое изменение. В приложениях WinForms и WPF используется Microsoft.NET.Sdk
description: Ознакомьтесь с критическим изменением в .NET 5.0, где приложения Windows Forms и Windows Presentation Framework теперь используют пакет SDK для .NET вместо .NET Core WinForms и пакета SDK WPF.
ms.date: 09/18/2020
ms.openlocfilehash: 5eafed03fbf034f6a6457217a8527a877214e239
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633823"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>В приложениях WinForms и WPF используется Microsoft.NET.Sdk

Приложения Windows Forms и Windows Presentation Framework (WPF) теперь используют пакет SDK для .NET (`Microsoft.NET.Sdk`) вместо .NET Core WinForms и пакета SDK WPF (`Microsoft.NET.Sdk.WindowsDesktop`).

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET Core в приложениях WinForms и WPF использовался отдельный [пакет SDK проекта](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`). Начиная с .NET 5.0 пакет SDK WinForms и WPF был объединен с пакетом SDK для .NET (`Microsoft.NET.Sdk`). Кроме того, новые [моникеры целевой платформы (TFM)](../../../../standard/frameworks.md) заменяют собой `netcoreapp` и `netstandard` в .NET 5. В следующем примере показаны изменения, которые необходимо внести для файла проекта WPF при изменении целевой платформы на .NET 5.0 или более поздней версии.

В предыдущих версиях .NET Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

В .NET 5.0 и более поздних версиях:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a>Представленная версия

Пакет SDK для .NET 5.0.100

## <a name="recommended-action"></a>Рекомендованное действие

В файле проекта WPF или Windows Forms:

- Измените атрибут `Sdk` на `Microsoft.NET.Sdk`.
- Установите для свойства `TargetFramework` значение `net5.0-windows`.

## <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
