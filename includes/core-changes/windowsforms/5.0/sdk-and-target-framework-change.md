---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656352"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>В приложениях WinForms и WPF используется Microsoft.NET.Sdk

Приложения Windows Forms и Windows Presentation Framework (WPF) теперь используют пакет SDK для .NET (`Microsoft.NET.Sdk`) вместо .NET Core WinForms и пакета SDK WPF (`Microsoft.NET.Sdk.WindowsDesktop`).

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET Core в приложениях WinForms и WPF использовался отдельный [пакет SDK проекта](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`). Начиная с .NET 5.0 пакет SDK WinForms и WPF был объединен с пакетом SDK для .NET (`Microsoft.NET.Sdk`). Кроме того, новые [моникеры целевой платформы (TFM)](../../../../docs/standard/frameworks.md) заменяют собой `netcoreapp` и `netstandard` в .NET 5. В следующем примере показаны изменения, которые необходимо внести для файла проекта WPF при изменении целевой платформы на .NET 5.0 или более поздней версии.

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

#### <a name="version-introduced"></a>Представленная версия

Предварительная версия 8 .NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

В файле проекта WPF или Windows Forms:

- Измените атрибут `Sdk` на `Microsoft.NET.Sdk`.
- Установите для свойства `TargetFramework` значение `net5.0-windows`.

#### <a name="category"></a>Категория

- Windows Forms
- Windows Presentation Foundation (WPF)

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
