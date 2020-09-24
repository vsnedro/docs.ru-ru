---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679007"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>Свойству OutputType задано значение WinExe для приложений WPF и WinForms

Свойству `OutputType` автоматически задано значение `WinExe` для приложений Windows Presentation Foundation (WPF) и Windows Forms. Если свойство `OutputType` имеет значение `WinExe`, окно консоли не открывается при выполнении приложения.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET используется значение, указанное для `OutputType` в файле проекта. Пример:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Начиная с .NET 5.0 свойству `OutputType` автоматически задается значение `WinExe` для приложений WPF и Windows Forms. Пример:

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a>Причина изменения

Предполагается, что большинство пользователей не хотят, чтобы окно консоли открывалось при выполнении приложения WPF или Windows Forms. Кроме того, [поскольку теперь эти типы приложений используют пакет SDK для .NET](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) вместо пакета SDK для Windows Desktop, будет задано правильное значение по умолчанию. При добавлении поддержки для использования iOS и Android в качестве целевых платформ будет проще работать с несколькими платформами, если все они используют один и тот же тип выходных данных.

#### <a name="version-introduced"></a>Представленная версия

Предварительная версия 8 .NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

Никаких действий выполнять не требуется. Однако если вы хотите восстановить старое поведение, задайте свойству `DisableWinExeOutputInference` значение `true` в файле проекта.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a>Категория

- Windows Forms
- Windows Presentation Foundation (WPF)

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
