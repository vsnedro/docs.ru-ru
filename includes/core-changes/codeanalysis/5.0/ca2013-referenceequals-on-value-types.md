---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065210"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="1b39e-101">CA2013: не используйте ReferenceEquals с типами значений</span><span class="sxs-lookup"><span data-stu-id="1b39e-101">CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="1b39e-102">Правило [CA2013](/visualstudio/code-quality/ca2013) анализатора кода .NET включено по умолчанию начиная с .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="1b39e-102">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="1b39e-103">Оно создает предупреждение сборки для любого кода, где для сравнения одного или нескольких типов значений на предмет равенства используется <xref:System.Object.ReferenceEquals(System.Object,System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="1b39e-103">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1b39e-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="1b39e-104">Change description</span></span>

<span data-ttu-id="1b39e-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="1b39e-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="1b39e-106">Некоторые из этих правил включены по умолчанию, в том числе [CA2013](/visualstudio/code-quality/ca2013).</span><span class="sxs-lookup"><span data-stu-id="1b39e-106">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="1b39e-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="1b39e-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="1b39e-108">Правило CA2013 находит экземпляры, где для сравнения одного или нескольких типов значений на предмет равенства используется <xref:System.Object.ReferenceEquals(System.Object,System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="1b39e-108">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="1b39e-109">Сравнение типов значений на предмет равенства таким образом может привести к неверным результатам, так как значения упаковываются до их сравнения.</span><span class="sxs-lookup"><span data-stu-id="1b39e-109">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="1b39e-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> будет возвращать `false` даже в том случае, если сравниваемые значения представляют один и тот же экземпляр типа значения.</span><span class="sxs-lookup"><span data-stu-id="1b39e-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1b39e-111">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="1b39e-111">Version introduced</span></span>

<span data-ttu-id="1b39e-112">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="1b39e-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1b39e-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="1b39e-113">Recommended action</span></span>

- <span data-ttu-id="1b39e-114">Измените код, чтобы использовать соответствующий оператор равенства, например `==`.</span><span class="sxs-lookup"><span data-stu-id="1b39e-114">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="1b39e-115">Не следует отключать это предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1b39e-115">You should not suppress this warning.</span></span>

- <span data-ttu-id="1b39e-116">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="1b39e-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="1b39e-117">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="1b39e-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="1b39e-118">Категория</span><span class="sxs-lookup"><span data-stu-id="1b39e-118">Category</span></span>

<span data-ttu-id="1b39e-119">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="1b39e-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1b39e-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1b39e-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
