---
ms.openlocfilehash: cd7860a5dfff1eb595625665382689733cffc94a
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90721277"
---
### <a name="ca1416-platform-compatibility"></a>CA1416. Совместимость платформ

Начиная с .NET 5.0 правило анализатора кода .NET [CA1416](/visualstudio/code-quality/ca1416) включено по умолчанию. Оно создает предупреждение сборки для вызовов API для конкретных платформ из мест вызовов, которые не проверяют операционную систему.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Некоторые из этих правил включены по умолчанию, в том числе [CA1416](/visualstudio/code-quality/ca1416). Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку. Правило CA1416 информирует вас об использовании API для конкретных платформ из мест, где контекст платформы не проверяется.

Правило [CA1416](/visualstudio/code-quality/ca1416), анализатор совместимости платформ, работает с другими функциями, которые являются новыми в .NET 5.0. В .NET 5.0 появились атрибуты <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> и <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, позволяющие указывать платформы, на которых API *поддерживается* или *не поддерживается*. В отсутствие этих атрибутов предполагается, что API поддерживается на всех платформах. Эти атрибуты применялись в API для конкретных платформ в основных библиотеках .NET.

В проектах, предназначенных для платформ, для которых используются недоступные API, правило [CA1416](/visualstudio/code-quality/ca1416) помечает любой вызов API, зависящий от платформы, где контекст платформы не проверяется. Большинство API, которые теперь снабжены атрибутами <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> и <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, вызывают исключения <xref:System.PlatformNotSupportedException>, когда они вызываются в неподдерживаемой операционной системе. Теперь, когда эти API отмечены как зависящие от платформы, правило [CA1416](/visualstudio/code-quality/ca1416) помогает предотвратить возникновение исключений <xref:System.PlatformNotSupportedException> во время выполнения, добавляя проверки ОС к местам вызовов.

#### <a name="examples"></a>Примеры

- Метод <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> поддерживается только в Windows (он дополнен `[SupportedOSPlatform("windows")]`). Следующий код выдаст предупреждение CA1416 во время сборки, если проект [предназначен](../../../../docs/standard/frameworks.md) для `net5.0` (но не для `net5.0-windows`). Действия, которые можно предпринять, чтобы избежать предупреждения, см. в разделе [Рекомендуемое действие](#recommended-action).

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- Метод <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> не поддерживается в браузере (он дополнен `[UnsupportedOSPlatform("browser")]`). Следующий код выдаст предупреждение CA1416 во время сборки, если проект использует пакет SDK Blazor WebAssembly (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) или включает `browser` в качестве поддерживаемой платформы (`<SupportedPlatform Include="browser" />`) в файле проекта.

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a>Представленная версия

5.0 (RC1)

#### <a name="recommended-action"></a>Рекомендованное действие

Убедитесь, что API, относящиеся к конкретной платформе, вызываются только при выполнении кода на соответствующей платформе. Вы можете проверить текущую операционную систему с помощью одного из методов `Is<Platform>` в классе <xref:System.OperatingSystem?displayProperty=nameWithType>. Например <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, перед вызовом API для конкретной платформы.

Можно использовать один из методов `Is<Platform>` в условии инструкции `if`:

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

Или, если вы не хотите использовать дополнительную инструкцию `if` во время выполнения, вызовите <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

Вы также можете отметить API как зависящий от платформы. В этом случае проверку требований будут выполнять вызывающие объекты. Можно отметить определенные методы или типы или всю сборку.

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

Если вы не хотите исправлять все места вызовов, можно выбрать один из следующих вариантов, чтобы отключить предупреждение.

- Если требуется отключить правило CA1416, это можно сделать с помощью `#pragma` или флага компилятора [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) или путем [установки серьезности правила](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) `none` в файле EDITORCONFIG.

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта. Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Категория

- Анализ кода
- Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

Для платформы Windows:

- все API, указанные в <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

Для платформы Blazor WebAssembly:

- все API, указанные в <https://github.com/dotnet/runtime/issues/41087>.

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a>См. также раздел

- [CA1416. Проверка совместимости платформ](/visualstudio/code-quality/ca1416)
- [Анализатор .NET API](../../../../docs/standard/analyzers/api-analyzer.md)
