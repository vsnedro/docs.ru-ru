---
title: Анализатор совместимости платформ
description: Анализатор Roslyn, который помогает обнаруживать проблемы совместимости платформ в кросс-платформенных приложениях и библиотеках.
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406591"
---
# <a name="platform-compatibility-analyzer"></a>Анализатор совместимости платформ

Вероятно, вы слышали девиз "единой платформы .NET" — единая, унифицированная платформа для создания приложений любого типа. Пакет SDK .NET 5.0 включает ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin и ML.NET. В будущем будет реализована поддержка и других платформ. ПО .NET 5.0 призвано предоставить вам возможности для работы с любыми вариантами .NET, но не пытается полностью абстрагировать базовую операционную систему (ОС). Вы сможете и далее вызывать API, зависящие от платформы, например привязки P/Invokes, WinRT или привязки Xamarin для iOS и Android.

Но использование в компоненте API, зависящих от платформы, означает, что код не будет работать на всех платформах. Нам требовался способ для выявления таких проблем на этапе разработки, чтобы разработчики могли получать диагностические сведения при неосмотрительном использовании зависящих от платформы API. Для этого .NET 5.0 в представлен [анализатор совместимости платформ](/visualstudio/code-quality/ca1416) и дополнительные API, которые позволяют разработчикам идентифицировать и при необходимости использовать API, зависящие от платформы.
Новые API включают следующее:

- <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> для аннотации API как зависящих от платформы и <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> для аннотации API как неподдерживаемых в определенной ОС. При необходимости эти атрибуты могут включать номер версии и уже применяться к некоторым API, зависящим от платформы, в основных библиотеках .NET.
- Статические методы `Is<Platform>()` и `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` в классе <xref:System.OperatingSystem?displayProperty=nameWithType> для безопасного вызова API, зависящих от платформы. Например, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> можно использовать для предложения условия вызова к API для Windows, а <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() — для предложения условия вызова к API для Windows с определенной версией. Подробные сведения о том, как такие методы можно использовать в качестве условий для ссылок на API, зависящие от платформы, см. в [этих примерах](#guard-platform-specific-apis-with-guard-methods).

> [!TIP]
> Анализатор совместимости платформ обновляет и заменяет функцию [Обнаружение проблем с межплатформенным взаимодействием](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) в [анализаторе API .NET](../../standard/analyzers/api-analyzer.md).

## <a name="prerequisites"></a>предварительные требования

Анализатор совместимости платформ является одним из анализаторов качества кода Roslyn. Начиная с .NET 5.0 эти анализаторы входят в состав [пакета SDK .NET](../../fundamentals/productivity/code-analysis.md). Анализатор совместимости платформ включен по умолчанию только для проектов, ориентированных на `net5.0` или более поздней версии. Но вы можете [включить](/visualstudio/code-quality/ca1416.md#configurability) его для проектов, ориентированных на другие платформы.

## <a name="how-the-analyzer-determines-platform-dependency"></a>Как анализатор определяет зависимость платформы

- Считается, что **API без атрибутов** работает на **всех платформах ОС**.
- Считается, что API с меткой `[SupportedOSPlatform("platform")]` можно переносить только на указанную платформу ОС `platform`.
  - Этот атрибут может применяться несколько раз для указания **поддержки нескольких платформ** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).
  - Анализатор выдаст **предупреждение**, если ссылки на API, зависящие от платформы, не включают надлежащий **контекст платформы**:
    - **Выдает предупреждение**, если проект не ориентирован на поддерживаемую платформу (например, вызов API ориентирован на Windows, а проект — на `<TargetFramework>net5.0-ios14.0</TargetFramework>`).
    - **Выдает предупреждение**, если проект ориентирован на несколько платформ (`<TargetFramework>net5.0</TargetFramework>`).
    - **Не выдает предупреждение**, если ссылки на API, зависящий от платформы, присутствуют в проекте, ориентированном на любую из **указанных платформ** (например, вызов API ориентирован на Windows, а проект — на `<TargetFramework>net5.0-windows</TargetFramework>`).
    - **Не выдает предупреждение**, если для API, зависящего от платформы, предлагается условие соответствующими методами проверки платформы (например, `if(OperatingSystem.IsWindows())`).
    - **Не выдает предупреждение**, если ссылки на API, зависящий от платформы, указаны в таком же зависящем от платформы контексте (**место вызова также имеет атрибут** `[SupportedOSPlatform("platform")`).
- API, помеченный `[UnsupportedOSPlatform("platform")]`, считается неподдерживаемым только на указанной платформе ОС `platform`, но поддерживается на всех других платформах.
  - Этот атрибут может применяться несколько раз с разными платформами, например `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.
  - Анализатор выдает **предупреждение** только в том случае, если `platform` действует для места вызова:
    - **Выдает предупреждение**, если проект ориентирован на платформу, которая имеет атрибут неподдерживаемой (например, если API имеет атрибут `[UnsupportedOSPlatform("windows")]`, а место вызова ориентировано на `<TargetFramework>net5.0-windows</TargetFramework>`).
    - **Выдает предупреждение**, если проект ориентирован на несколько платформ, а атрибут `platform` включен в группу элементов [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) или атрибут `platform` вручную включен в группу элементов `MSBuild` \<SupportedPlatform>:

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - **Не выдает предупреждение**, если вы выполняете сборку приложения, которое не ориентировано на неподдерживаемую платформу или ориентировано на несколько платформ, и платформа не включена в группу элементов [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) по умолчанию.
- Экземпляры обоих атрибутов могут быть созданы с номерами версий в составе имени платформы или без них.
  - Номера версий имеют формат `major.minor[.build[.revision]]`; `major.minor` — это обязательная часть, а `build` и `revision` — необязательные. Например, "Windows7.0" указывает на Windows версии 7.0, но часть "Windows" интерпретируется как Windows 0.0.

Дополнительные сведения см. в разделе с [примерами работы атрибутов и выдаваемых ими диагностических данных](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).

### <a name="advanced-scenarios-for-combining-attributes"></a>Расширенные сценарии для сочетания атрибутов

- Если задано сочетание атрибутов `[SupportedOSPlatform]` и `[UnsupportedOSPlatform]`, все атрибуты группируются по идентификатору платформы ОС:
  - **Список "Только поддерживаемые".** Если самая ранняя версия для каждой платформы ОС задана атрибутом `[SupportedOSPlatform]`, API считается таким, который поддерживается только указанными платформами и не поддерживается всеми другими. Необязательные атрибуты `[UnsupportedOSPlatform]` для каждой платформы могут иметь только более позднюю версию минимально поддерживаемой версии, что обозначает удаление API начиная с указанной версии.

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - **Список "Только неподдерживаемые".** Если самая ранняя версия для каждой платформы ОС задана атрибутом `[UnsupportedOSPlatform]`, API считается таким, который не поддерживается только указанными платформами и поддерживается всеми другими. Список может включать атрибут `[SupportedOSPlatform]` с такой же платформой, но более поздней версии, что означает поддержку API начиная с такой версии.
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - **Список "Несогласованные".** Если самая ранняя версия для некоторых платформ указана как `[SupportedOSPlatform]`, но для других платформ — как `[UnsupportedOSPlatform]`, она считается несогласованной, что не поддерживается в анализаторе.
  - Если самые ранние версии `[SupportedOSPlatform]` и атрибуты `[UnsupportedOSPlatform]` равны, анализатор считает, что платформа входит в **список только поддерживаемых**.
- Атрибуты платформы могут применяться к типам, элементам (методам, полям, свойствам и событиями) и сборкам с разными именами и (или) версиями платформ.
  - Атрибуты, применяемые к целевой платформе `target` верхнего уровня, также применяются ко всем ее элементам и типам.
  - Атрибуты дочернего уровня применяются только в том случае, если они соответствуют правилу "Дочерние аннотации могут ограничивать поддержку платформ, но не могут расширять ее".
    - Если родительский элемент включает список **Только поддерживаемые**, атрибуты дочернего элемента не смогут добавить поддержку новой платформы, так как это приведет к расширению поддержки родительского элемента. Поддержку новой платформы можно добавить только к самому родительскому элементу. Но он может включать атрибут `Supported` для такой же платформы более поздних версий, поскольку это сужает поддержку. Кроме того, он может включать атрибут `Unsupported` с такой же платформой, так как это также сужает поддержку в родительском элементе.
    - Если родительский элемент включает список **Только неподдерживаемые**, атрибуты дочернего элемента могут добавить поддержку новой платформы, так как это сужает поддержку в родительском элементе. Но он не может включать атрибут `Supported` для такой же платформы, которая задана родительским элементом, ведь это приведет к расширению поддержки последнего. Поддержку одной платформы можно добавить только на уровне родительского элемента, на котором применяется исходный атрибут `Unsupported`.
  - Если `[SupportedOSPlatform("platformVersion")]` применяется более одного раза для API с одинаковым именем `platform`, анализатор будет обрабатывать только атрибут с минимальной версией.
  - Если `[UnsupportedOSPlatform("platformVersion")]` применяется более двух раз для API с одинаковым именем `platform`, анализатор будет обрабатывать только два атрибута с минимальными версиями.
  
  > [!NOTE]
  > Поддержка API, который изначально поддерживался, но больше не поддерживается в поздней версии, не будет возобновлена в еще более поздних версиях.

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a>Примеры работы атрибутов и выдаваемых ими диагностических данных

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a>Обработка выданных предупреждений

При анализе таких диагностических данных рекомендуется использовать только соответствующие для конкретной платформы API, зависящие от платформы. Ниже приведены варианты по обработке предупреждений. Выберите оптимальный вариант для своей ситуации:

- **Предложение условий для вызова.** Это можно сделать, направив условный вызов к коду во время выполнения. Проверьте, выполняется ли код на нужной платформе `Platform` с помощью одного из методов проверки платформы, например `OperatingSystem.Is<Platform>()` или `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.

- **Установка для места вызова метки зависимости от платформы.** Вы также можете пометить свои API как зависящие от платформы, благодаря чему требования будут смещены на вызывающие методы. Пометьте содержащий метод, тип или всю сборку такими же атрибутами, что и зависящий от платформы вызов, на который указывает ссылка. [Примеры](#mark-call-site-as-platform-specific).

- **Утверждение места вызова с помощью проверки платформы.** Если вы не хотите применять дополнительную инструкцию `if` во время выполнения, используйте <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>. [Пример.](#assert-the-call-site-with-platform-check)

- **Удаление кода.** Обычно это нежелательно, так как в таком случае теряется точность, если с вашим кодом работают пользователи Windows. В случаях с доступностью кросс-платформенной альтернативы чаще оптимальнее использовать ее, а не API, зависимые от платформы.

- **Блокировать предупреждение.** Вы также можете заблокировать предупреждение с помощью файла editor.config или инструкции `#pragma warning disable ca1416`. Но прибегайте к этому варианту только в исключительных случаях при использовании API, зависящих от платформы.

### <a name="guard-platform-specific-apis-with-guard-methods"></a>Предложение условий для API, зависящих от платформы, с помощью методов условий

Имя платформы в методе условия должно совпадать с именем платформы вызывающего API, зависимого от платформы. Если строка платформы вызывающего API включает версию:

- Для атрибута `[SupportedOSPlatform("platformVersion")]` значение для платформы метода условия `version` должно быть больше или равно значению `Version` вызывающей платформы.
- Для атрибута `[UnsupportedOSPlatform("platformVersion")]` значение для платформы метода условия `version` должно быть меньше или равно значению `Version` вызывающей платформы.

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- Если вам необходимо предложить условие для кода, который ориентирован на netstandard или netcoreapp, в которых новые API <xref:System.OperatingSystem> недоступны, вы можете использовать API <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType>, который обрабатывается анализатором. Но он менее производителен, чем API, добавленные в <xref:System.OperatingSystem>. Если платформа не поддерживается в структуре <xref:System.Runtime.InteropServices.OSPlatform>, вы можете использовать метод <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType> который также обрабатывается анализатором.

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a>Установка для места вызова метки зависимости от платформы

Имена платформ должны совпадать с API, зависимым от вызывающей платформы. Если строка платформы включает версию:

- Для атрибута `[SupportedOSPlatform("platformVersion")]` значение для платформы места вызова `version` должно быть больше или равно значению `Version` вызывающей платформы.
- Для атрибута `[UnsupportedOSPlatform("platformVersion")]` значение для платформы места вызова `version` должно быть меньше или равно значению `Version` вызывающей платформы.

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a>Утверждение места вызова с помощью проверки платформы

Все условные проверки, используемые в [примерах условий платформы](#guard-platform-specific-apis-with-guard-methods), также можно использовать в качестве условия для <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a>См. также раздел

- [Имена целевых платформ в .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [Создание аннотаций для API, зависящих от платформ, и обнаружение использования этой функции](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [Создание аннотаций для API как неподдерживаемых на конкретных платформах](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [CA1416: анализатор совместимости платформ](/visualstudio/code-quality/ca1416)
- [Анализатор .NET API](../../standard/analyzers/api-analyzer.md)
