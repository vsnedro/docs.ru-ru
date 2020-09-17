---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065171"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="57d23-101">CA1417. OutAttribute в строковом параметре для P/Invoke</span><span class="sxs-lookup"><span data-stu-id="57d23-101">CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="57d23-102">Правило [CA1417](/visualstudio/code-quality/ca1417) анализатора кода .NET включено по умолчанию начиная с .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="57d23-102">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="57d23-103">Оно создает предупреждение сборки для любого определения метода [вызова неуправляемого кода (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md), в которых параметр <xref:System.String> передается по значению и отмечается с помощью <xref:System.Runtime.InteropServices.OutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="57d23-103">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="57d23-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="57d23-104">Change description</span></span>

<span data-ttu-id="57d23-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="57d23-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="57d23-106">Некоторые из этих правил включены по умолчанию, включая [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="57d23-106">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="57d23-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="57d23-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="57d23-108">Флаги правила CA1417 определения методов [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md), в которых параметр <xref:System.String> отмечен атрибутом <xref:System.Runtime.InteropServices.OutAttribute> и передается по значению.</span><span class="sxs-lookup"><span data-stu-id="57d23-108">Rule CA1417 flags [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="57d23-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="57d23-109">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="57d23-110">Среда выполнения .NET поддерживает таблицу, называемую пулом интернирования, которая содержит одну ссылку на каждую уникальную строку литерала в программе.</span><span class="sxs-lookup"><span data-stu-id="57d23-110">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="57d23-111">Если интернированная строка, помеченная <xref:System.Runtime.InteropServices.OutAttribute>, передается по значению в метод P/Invoke, среду выполнения можно дестабилизировать.</span><span class="sxs-lookup"><span data-stu-id="57d23-111">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="57d23-112">Дополнительные сведения об интернировании строк см. в разделе примечаний для <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57d23-112">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="57d23-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="57d23-113">Version introduced</span></span>

<span data-ttu-id="57d23-114">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="57d23-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="57d23-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="57d23-115">Recommended action</span></span>

- <span data-ttu-id="57d23-116">Если необходимо выполнить маршалирование измененных строковых данных обратно в вызывающий объект, передайте строку по ссылке.</span><span class="sxs-lookup"><span data-stu-id="57d23-116">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="57d23-117">Если вам не нужно маршалировать измененные строковые данные обратно вызывающему объекту, просто удалите <xref:System.Runtime.InteropServices.OutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="57d23-117">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="57d23-118">Дополнительные сведения в разделе [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="57d23-118">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="57d23-119">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="57d23-119">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="57d23-120">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="57d23-120">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="57d23-121">Категория</span><span class="sxs-lookup"><span data-stu-id="57d23-121">Category</span></span>

<span data-ttu-id="57d23-122">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="57d23-122">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="57d23-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="57d23-123">Affected APIs</span></span>

<span data-ttu-id="57d23-124">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="57d23-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
