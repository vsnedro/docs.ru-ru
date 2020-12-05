---
title: Анализ кода в .NET
titleSuffix: ''
description: Сведения об анализе исходного кода в пакете SDK для .NET.
ms.date: 08/22/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 8efac4d5e3fddcb9fdc6e08bcc933f2776420ced
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739978"
---
# <a name="overview-of-net-source-code-analysis"></a>Обзор анализа исходного кода .NET

Анализаторы .NET Compiler Platform (Roslyn) проверяют качество кода C# или Visual Basic и выявляют в нем проблемы. Начиная с .NET 5.0 эти анализаторы входят в состав пакета SDK .NET. Если вы не хотите переходить на пакет SDK для .NET 5 + или если предпочитаете использовать модель на основе пакетов NuGet, анализаторы также доступны в `Microsoft.CodeAnalysis.NetAnalyzers` [пакете NuGet](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers). Вы можете предпочесть модели на основе пакетов для обновления версий по требованию.

> [!NOTE]
> Анализаторы .NET являются независимыми от целевой платформы. То есть проект не обязан ориентироваться на конкретную платформу .NET. Анализаторы работают для проектов, предназначенных для, а также для `net5.0` более ранних версий .NET, таких как `netcoreapp` , `netstandard` и `net472` .

- [Анализ качества кода (правила "Какскскскс")](#code-quality-analysis)
- [Анализ стиля кода (правила "Идекскскскс")](#code-style-analysis)

Если анализатор обнаруживает нарушения правил, они включаются в отчет как предложение, предупреждение или ошибку в зависимости от того, как [настроено](configuration-options.md)каждое правило. Нарушения анализа кода отображаются с префиксом "CA" или "IDE", чтобы отличать их от ошибок компилятора.

> [!TIP]
>
> - Можно также установить сторонние анализаторы, такие как [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Рослинатор](https://www.nuget.org/packages/Roslynator.Analyzers/), [xUnit Analyzers](https://www.nuget.org/packages/xunit.analyzers/)и [анализатор Sonar](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).
> - Если вы используете Visual Studio, то многие правила анализатора связаны с *исправлениями кода* , которые можно применить для устранения проблемы. Исправления кода отображаются в меню значка лампочки.

## <a name="code-quality-analysis"></a>Анализ качества кода

_Правила анализа качества кода (CA)_ проверяют код C# или Visual Basic для обеспечения безопасности, производительности, проектирования и других проблем. По умолчанию для проектов, предназначенных для .NET 5,0 или более поздней версии, включен анализ. Вы можете включить анализ кода для проектов, предназначенных для более ранних версий .NET, задав для свойства [енабленетанализерс](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) значение `true` . Можно также отключить анализ кода для проекта, задав для значение `EnableNETAnalyzers` `false` .

> [!TIP]
> В Visual Studio можно включить или отключить анализ кода с помощью окно свойств проекта. Чтобы получить доступ к окно свойств проекта, щелкните правой кнопкой мыши проект в обозреватель решений и выберите пункт **Свойства**. Затем перейдите на вкладку **анализ кода** и установите или снимите флажок, чтобы **включить анализаторы .NET**.

### <a name="enabled-rules"></a>Включенные правила

По умолчанию в .NET 5,0 Preview 8 включены следующие правила.

| ИД диагностики | Категория | Статус | Описание |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Совместимость | Предупреждение | Анализатор совместимости платформ |
| [CA1417](/visualstudio/code-quality/ca1417) | Совместимость | Предупреждение | Не используйте `OutAttribute` в строковых параметрах для P/Invoke |
| [CA1831](/visualstudio/code-quality/ca1831) | Производительность | Предупреждение | Используйте `AsSpan` вместо индексаторов на основе диапазона для строки, если это уместно |
| [CA2013](/visualstudio/code-quality/ca2013) | Надежность | Предупреждение | Не используйте `ReferenceEquals` с типами значений |
| [CA2014](/visualstudio/code-quality/ca2014) | Надежность | Предупреждение | Не используйте `stackalloc` в циклах |
| [CA2015](/visualstudio/code-quality/ca2015) | Надежность | Предупреждение | Не определяйте методы завершения для типов, производных от <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Использование | Предупреждение | Повторно порождайте исключения для сохранения сведений стека
| [CA2247](/visualstudio/code-quality/ca2247) | Использование | Предупреждение | Аргумент, переданный в конструктор TaskCompletionSource, должен быть <xref:System.Threading.Tasks.TaskCreationOptions> перечислением, а не <xref:System.Threading.Tasks.TaskContinuationOptions> |

Можно изменить серьезность этих правил, чтобы отключить их или повысить их уровень до ошибок.

Полный список доступных правил качества кода см. в разделе [Правила качества кода](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Включить дополнительные правила

Начиная с .NET 5.0 RC2 пакет SDK для .NET поставляется со всеми [правилами качества кода "CA"](/visualstudio/code-quality/code-analysis-for-managed-code-warnings). Полный список правил, которые входят в состав каждой версии пакета SDK для .NET, см. в статье [выпуски анализатора](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

#### <a name="default-analysis-mode"></a>Режим анализа по умолчанию

В режиме анализа по умолчанию некоторые правила [по умолчанию включены](#enabled-rules) как предупреждения сборки. Некоторые другие правила по умолчанию включены только в предложениях интегрированной среды разработки Visual Studio с соответствующими исправлениями кода. Остальные правила по умолчанию отключены. [Полный список правил](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md) включает уровень серьезности по умолчанию для каждого правила и то, включено ли правило по умолчанию в режим анализа по умолчанию.

#### <a name="custom-analysis-mode"></a>Пользовательский режим анализа

Можно [настроить правила анализа кода](configuration-options.md) , чтобы включить или отключить отдельное правило или категорию правил. Кроме того, можно использовать свойство [аналисисмоде](../../core/project-sdk/msbuild-props.md#analysismode) для переключения на один из следующих пользовательских режимов анализа:

- _Агрессивный_ или режим _отказа_ . все правила по умолчанию включены как предупреждения сборки. Вы можете выборочно [отказаться](configuration-options.md) от отдельных правил, чтобы отключить их.
- _Консервативный_ или _явный_ режим. по умолчанию все правила отключены. Можно выборочно [принять](configuration-options.md) отдельные правила, чтобы включить их.

### <a name="treat-warnings-as-errors"></a>Рассматривать предупреждения как ошибки

При использовании `-warnaserror` флага при построении проектов все предупреждения анализа кода также обрабатываются как ошибки. Если вы не хотите, чтобы предупреждения качества кода обрабатывались как ошибки в присутствии `-warnaserror` , можно задать `CodeAnalysisTreatWarningsAsErrors` для свойства MSBuild значение `false` в файле проекта.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

Вы по-прежнему увидите предупреждения анализа кода, но они не нарушат сборку.

### <a name="latest-updates"></a>Последние обновления

По умолчанию при обновлении до более новых версий пакета SDK для .NET вы получите последние правила анализа кода и серьезность правил по умолчанию. Если вы не хотите этого делать, например, если вы хотите убедиться, что новые правила не включены или отключены, их можно переопределить одним из следующих способов.

- Задайте `AnalysisLevel` для свойства MSBuild определенное значение, чтобы заблокировать предупреждения для этого набора. При обновлении до более нового пакета SDK вы по-прежнему получаете исправления ошибок для этих предупреждений, но новые предупреждения не будут включены, а существующие предупреждения не будут отключены. Например, чтобы заблокировать набор правил для тех, которые поставляются с пакетом SDK для .NET версии 5,0, добавьте следующую запись в файл проекта.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > Значение свойства по умолчанию `AnalysisLevel` — `latest` , что означает, что вы всегда получаете последние правила анализа кода при переходе на более новые версии пакета SDK для .NET.

  Дополнительные сведения и список возможных значений см. в разделе [аналисислевел](../../core/project-sdk/msbuild-props.md#analysislevel).

- Установите [пакет NuGet Microsoft. CodeAnalysis. нетанализерс](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) для отделения обновлений правил от обновлений пакета SDK для .NET. При установке пакета отключаются встроенные анализаторы SDK и создается предупреждение о сборке, если пакет SDK содержит более новую версию сборки анализатора, чем версия пакета NuGet.

## <a name="code-style-analysis"></a>Анализ стиля кода

[Анализ стиля кода](/visualstudio/ide/editorconfig-code-style-settings-reference) (правила "идекскскскс") позволяет определять и поддерживать единообразный стиль кода в базе кода. Ниже приведены параметры по умолчанию.

- Сборка из командной строки: анализ стиля кода по умолчанию отключен для всех проектов .NET при сборке из командной строки.
- Visual Studio: анализ стиля кода включен по умолчанию для всех проектов .NET в Visual Studio в виде [быстрых действий по оптимизации кода](/visualstudio/ide/code-generation-in-visual-studio).

Начиная с .NET 5,0 RC2 можно включить анализ стиля кода для сборки как в командной строке, так и в Visual Studio. Нарушения стиля кода отображаются как предупреждения или ошибки с префиксом "IDE". Это позволяет применять единообразные стили кода во время сборки.

> [!NOTE]
> Функция анализа стиля кода экспериментальна и может изменяться между выпусками .NET 5 и .NET 6.

Инструкции по включению анализа стиля кода для сборки:

1. Задайте для свойства MSBuild [енфорцекодестилеинбуилд](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) значение `true` .

1. В *editorconfig* -файле [Настройте](configuration-options.md) каждое правило стиля кода "IDE", которое вы хотите запускать при сборке как предупреждение или ошибку. Пример:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Кроме того, можно настроить всю категорию "Style" как предупреждение или ошибку, по умолчанию, а затем выборочно отключить правила, которые не нужно запускать при сборке. Пример:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

## <a name="suppress-a-warning"></a>Подавлять предупреждение

Чтобы отключить нарушение правил, задайте для этого идентификатора правила степень серьезности `none` в файле EditorConfig. Пример:

```ini
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio предоставляет дополнительные способы отключения предупреждений из правил анализа кода. Дополнительные сведения см. в разделе [подавлять нарушения](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Дополнительные сведения о серьезности правил см. в разделе [Настройка серьезности правила](configuration-options.md#severity-level).

## <a name="see-also"></a>См. также

- [Справочник по правилам анализа качества кода](quality-rules/index.md)
- [Справочник по правилам анализа стиля кода](style-rules/index.md)
- [Анализ кода в Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [Пакет SDK для .NET Compiler Platform](../../csharp/roslyn-sdk/index.md)
- [Учебник. Создание средства для анализа и исправления кода](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
