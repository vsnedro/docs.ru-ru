---
ms.openlocfilehash: 4a7616d2ffaabab5279342ebc1082c93a174a52d
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406181"
---
### <a name="ca1416-platform-compatibility"></a><span data-ttu-id="b7307-101">CA1416. Совместимость платформ</span><span class="sxs-lookup"><span data-stu-id="b7307-101">CA1416: Platform compatibility</span></span>

<span data-ttu-id="b7307-102">Начиная с .NET 5.0 правило анализатора кода .NET [CA1416](/visualstudio/code-quality/ca1416) включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7307-102">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="b7307-103">Оно создает предупреждение сборки для вызовов API для конкретных платформ из мест вызовов, которые не проверяют операционную систему.</span><span class="sxs-lookup"><span data-stu-id="b7307-103">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b7307-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="b7307-104">Change description</span></span>

<span data-ttu-id="b7307-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="b7307-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="b7307-106">Некоторые из этих правил включены по умолчанию, в том числе [CA1416](/visualstudio/code-quality/ca1416).</span><span class="sxs-lookup"><span data-stu-id="b7307-106">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="b7307-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="b7307-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="b7307-108">Правило CA1416 информирует вас об использовании API для конкретных платформ из мест, где контекст платформы не проверяется.</span><span class="sxs-lookup"><span data-stu-id="b7307-108">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="b7307-109">Правило [CA1416](/visualstudio/code-quality/ca1416), анализатор совместимости платформ, работает с другими функциями, которые являются новыми в .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="b7307-109">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="b7307-110">В .NET 5.0 появились атрибуты <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> и <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, позволяющие указывать платформы, на которых API *поддерживается* или *не поддерживается*.</span><span class="sxs-lookup"><span data-stu-id="b7307-110">.NET 5.0 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="b7307-111">В отсутствие этих атрибутов предполагается, что API поддерживается на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="b7307-111">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="b7307-112">Эти атрибуты применялись в API для конкретных платформ в основных библиотеках .NET.</span><span class="sxs-lookup"><span data-stu-id="b7307-112">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="b7307-113">В проектах, предназначенных для платформ, для которых используются недоступные API, правило [CA1416](/visualstudio/code-quality/ca1416) помечает любой вызов API, зависящий от платформы, где контекст платформы не проверяется.</span><span class="sxs-lookup"><span data-stu-id="b7307-113">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="b7307-114">Большинство API, которые теперь снабжены атрибутами <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> и <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, вызывают исключения <xref:System.PlatformNotSupportedException>, когда они вызываются в неподдерживаемой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b7307-114">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="b7307-115">Теперь, когда эти API отмечены как зависящие от платформы, правило [CA1416](/visualstudio/code-quality/ca1416) помогает предотвратить возникновение исключений <xref:System.PlatformNotSupportedException> во время выполнения, добавляя проверки ОС к местам вызовов.</span><span class="sxs-lookup"><span data-stu-id="b7307-115">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

#### <a name="examples"></a><span data-ttu-id="b7307-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="b7307-116">Examples</span></span>

- <span data-ttu-id="b7307-117">Метод <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> поддерживается только в Windows и декорируется `[SupportedOSPlatform("windows")]`.</span><span class="sxs-lookup"><span data-stu-id="b7307-117">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows and is decorated with `[SupportedOSPlatform("windows")]`.</span></span> <span data-ttu-id="b7307-118">Следующий код выдаст предупреждение CA1416 во время сборки, если проект [предназначен](../../../../docs/standard/frameworks.md) для `net5.0` (но не для `net5.0-windows`).</span><span class="sxs-lookup"><span data-stu-id="b7307-118">The following code will produce a CA1416 warning at build time if the project [targets](../../../../docs/standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="b7307-119">Действия, которые можно предпринять, чтобы избежать предупреждения, см. в разделе [Рекомендуемое действие](#recommended-action).</span><span class="sxs-lookup"><span data-stu-id="b7307-119">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="b7307-120">Метод <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> не поддерживается в браузере и декорируется `[UnsupportedOSPlatform("browser")]`.</span><span class="sxs-lookup"><span data-stu-id="b7307-120">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser and is decorated with `[UnsupportedOSPlatform("browser")]`.</span></span> <span data-ttu-id="b7307-121">Следующий код выдаст предупреждение CA1416 во время сборки, если проект поддерживает платформу браузера.</span><span class="sxs-lookup"><span data-stu-id="b7307-121">The following code will produce a CA1416 warning at build time if the project supports the browser platform.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - <span data-ttu-id="b7307-122">Проекты Blazor WebAssembly и проекты библиотеки классов Razor включают поддержку браузера автоматически.</span><span class="sxs-lookup"><span data-stu-id="b7307-122">Blazor WebAssembly projects and Razor class library projects include browser support automatically.</span></span>
  > - <span data-ttu-id="b7307-123">Чтобы вручную добавить браузер в качестве поддерживаемой платформы для проекта, добавьте следующую запись в файл проекта:</span><span class="sxs-lookup"><span data-stu-id="b7307-123">To manually add the browser as a supported platform for your project, add the following entry to your project file:</span></span>
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

#### <a name="version-introduced"></a><span data-ttu-id="b7307-124">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b7307-124">Version introduced</span></span>

<span data-ttu-id="b7307-125">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="b7307-125">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b7307-126">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b7307-126">Recommended action</span></span>

<span data-ttu-id="b7307-127">Убедитесь, что API, относящиеся к конкретной платформе, вызываются только при выполнении кода на соответствующей платформе.</span><span class="sxs-lookup"><span data-stu-id="b7307-127">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="b7307-128">Вы можете проверить текущую операционную систему с помощью одного из методов `Is<Platform>` в классе <xref:System.OperatingSystem?displayProperty=nameWithType>. Например <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, перед вызовом API для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="b7307-128">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="b7307-129">Можно использовать один из методов `Is<Platform>` в условии инструкции `if`:</span><span class="sxs-lookup"><span data-stu-id="b7307-129">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="b7307-130">Или, если вы не хотите использовать дополнительную инструкцию `if` во время выполнения, вызовите <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7307-130">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="b7307-131">Если вы создаете библиотеку, вы можете пометить API как зависящий от платформы.</span><span class="sxs-lookup"><span data-stu-id="b7307-131">If you're authoring a library, you can mark your API as platform-specific.</span></span> <span data-ttu-id="b7307-132">В этом случае проверку требований будут выполнять вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="b7307-132">In this case, the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="b7307-133">Можно отметить определенные методы или типы или всю сборку.</span><span class="sxs-lookup"><span data-stu-id="b7307-133">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="b7307-134">Если вы не хотите исправлять все места вызовов, можно выбрать один из следующих вариантов, чтобы отключить предупреждение.</span><span class="sxs-lookup"><span data-stu-id="b7307-134">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="b7307-135">Если требуется отключить правило CA1416, это можно сделать с помощью `#pragma` или флага компилятора [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) или путем [установки серьезности правила](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) `none` в файле EDITORCONFIG.</span><span class="sxs-lookup"><span data-stu-id="b7307-135">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="b7307-136">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b7307-136">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="b7307-137">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="b7307-137">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="b7307-138">Категория</span><span class="sxs-lookup"><span data-stu-id="b7307-138">Category</span></span>

- <span data-ttu-id="b7307-139">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="b7307-139">Code analysis</span></span>
- <span data-ttu-id="b7307-140">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="b7307-140">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b7307-141">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b7307-141">Affected APIs</span></span>

<span data-ttu-id="b7307-142">Для платформы Windows:</span><span class="sxs-lookup"><span data-stu-id="b7307-142">For Windows platform:</span></span>

- <span data-ttu-id="b7307-143">все API, указанные в <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span><span class="sxs-lookup"><span data-stu-id="b7307-143">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="b7307-144">Для платформы Blazor WebAssembly:</span><span class="sxs-lookup"><span data-stu-id="b7307-144">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="b7307-145">все API, указанные в <https://github.com/dotnet/runtime/issues/41087>.</span><span class="sxs-lookup"><span data-stu-id="b7307-145">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a><span data-ttu-id="b7307-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7307-146">See also</span></span>

- [<span data-ttu-id="b7307-147">CA1416. Проверка совместимости платформ</span><span class="sxs-lookup"><span data-stu-id="b7307-147">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="b7307-148">Анализатор .NET API</span><span class="sxs-lookup"><span data-stu-id="b7307-148">.NET API analyzer</span></span>](../../../../docs/standard/analyzers/api-analyzer.md)
