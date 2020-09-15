---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065176"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="da2b4-101">CA2015: не определяйте методы завершения для типов, производных от MemoryManager\<T></span><span class="sxs-lookup"><span data-stu-id="da2b4-101">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="da2b4-102">Правило [CA2015](/visualstudio/code-quality/ca2015) анализатора кода .NET включено по умолчанию, начиная с .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="da2b4-102">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="da2b4-103">Оно создает предупреждение сборки для всех типов, производных от <xref:System.Buffers.MemoryManager%601>, определяющих метод завершения.</span><span class="sxs-lookup"><span data-stu-id="da2b4-103">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

#### <a name="change-description"></a><span data-ttu-id="da2b4-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="da2b4-104">Change description</span></span>

<span data-ttu-id="da2b4-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="da2b4-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="da2b4-106">Некоторые из этих правил включены по умолчанию, в том числе [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="da2b4-106">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="da2b4-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="da2b4-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="da2b4-108">Правило CA2015 помечает типы, производные от <xref:System.Buffers.MemoryManager%601>, которые определяют метод завершения.</span><span class="sxs-lookup"><span data-stu-id="da2b4-108">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="da2b4-109">Добавление метода завершения в тип, производный от <xref:System.Buffers.MemoryManager%601>, скорее всего, свидетельствует об ошибке.</span><span class="sxs-lookup"><span data-stu-id="da2b4-109">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="da2b4-110">Предполагается, что собственный ресурс, который мог быть получен в <xref:System.Span%601>, очищается, даже если он по-прежнему используется <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="da2b4-110">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="da2b4-111">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="da2b4-111">Version introduced</span></span>

<span data-ttu-id="da2b4-112">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="da2b4-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="da2b4-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="da2b4-113">Recommended action</span></span>

- <span data-ttu-id="da2b4-114">Удалите определение метода завершения.</span><span class="sxs-lookup"><span data-stu-id="da2b4-114">Remove the finalizer definition.</span></span> <span data-ttu-id="da2b4-115">См. раздел [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="da2b4-115">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="da2b4-116">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="da2b4-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="da2b4-117">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="da2b4-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="da2b4-118">Категория</span><span class="sxs-lookup"><span data-stu-id="da2b4-118">Category</span></span>

<span data-ttu-id="da2b4-119">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="da2b4-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="da2b4-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="da2b4-120">Affected APIs</span></span>

<span data-ttu-id="da2b4-121">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="da2b4-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
