---
title: Критическое изменение. Свойству OutputType задано значение WinExe для приложений WPF и WinForms
description: Сведения о критическом изменении в .NET 5.0, где свойству OutputType автоматически задается значение WinExe для приложений Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760021"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>Свойству OutputType задано значение WinExe для приложений WPF и WinForms

Свойству `OutputType` автоматически задано значение `WinExe` для приложений Windows Presentation Foundation (WPF) и Windows Forms. Если свойство `OutputType` имеет значение `WinExe`, окно консоли не открывается при выполнении приложения.

## <a name="change-description"></a>Описание изменений

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

## <a name="reason-for-change"></a>Причина изменения

Предполагается, что большинство пользователей не хотят, чтобы окно консоли открывалось при выполнении приложения WPF или Windows Forms. Кроме того, [поскольку теперь эти типы приложений используют пакет SDK для .NET](sdk-and-target-framework-change.md) вместо пакета SDK для Windows Desktop, будет задано правильное значение по умолчанию. При добавлении поддержки для использования iOS и Android в качестве целевых платформ будет проще работать с несколькими платформами, если все они используют один и тот же тип выходных данных.

## <a name="version-introduced"></a>Представленная версия

.NET 5.0

## <a name="recommended-action"></a>Рекомендованное действие

Никаких действий выполнять не требуется. Однако если вы хотите восстановить старое поведение, задайте свойству `DisableWinExeOutputInference` значение `true` в файле проекта.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
