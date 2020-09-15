---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065189"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="180ac-101">CA2247: аргумент для конструктора TaskCompletionSource должен соответствовать значению TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="180ac-101">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="180ac-102">Правило [CA2247](/visualstudio/code-quality/ca2247) анализатора кода .NET включено по умолчанию, начиная с .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="180ac-102">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="180ac-103">Оно создает предупреждение сборки для вызовов конструктора <xref:System.Threading.Tasks.TaskCompletionSource%601>, которые передают аргумент типа <xref:System.Threading.Tasks.TaskContinuationOptions>.</span><span class="sxs-lookup"><span data-stu-id="180ac-103">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="180ac-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="180ac-104">Change description</span></span>

<span data-ttu-id="180ac-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="180ac-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="180ac-106">Некоторые из этих правил включены по умолчанию, в том числе [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="180ac-106">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="180ac-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="180ac-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="180ac-108">Правило CA2247 находит вызовы конструктора <xref:System.Threading.Tasks.TaskCompletionSource%601>, которые передают аргумент типа <xref:System.Threading.Tasks.TaskContinuationOptions>.</span><span class="sxs-lookup"><span data-stu-id="180ac-108">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="180ac-109">Тип <xref:System.Threading.Tasks.TaskCompletionSource%601> имеет конструктор, принимающий значение <xref:System.Threading.Tasks.TaskCreationOptions>, и другой конструктор, принимающий <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="180ac-109">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="180ac-110">Если вы случайно передадите значение <xref:System.Threading.Tasks.TaskContinuationOptions> вместо значения <xref:System.Threading.Tasks.TaskCreationOptions>, конструктор с параметром <xref:System.Object> будет вызван во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="180ac-110">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="180ac-111">Код будет компилироваться и выполняться, но поведение будет отличаться от ожидаемого.</span><span class="sxs-lookup"><span data-stu-id="180ac-111">Your code will compile and run but won't have the intended behavior.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="180ac-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="180ac-112">Version introduced</span></span>

<span data-ttu-id="180ac-113">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="180ac-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="180ac-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="180ac-114">Recommended action</span></span>

- <span data-ttu-id="180ac-115">Замените аргумент <xref:System.Threading.Tasks.TaskContinuationOptions> соответствующим значением <xref:System.Threading.Tasks.TaskCreationOptions>.</span><span class="sxs-lookup"><span data-stu-id="180ac-115">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="180ac-116">Не отключайте это предупреждение, так как оно почти всегда выделяет ошибку в коде.</span><span class="sxs-lookup"><span data-stu-id="180ac-116">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="180ac-117">См. раздел [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="180ac-117">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="180ac-118">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="180ac-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="180ac-119">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="180ac-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="180ac-120">Категория</span><span class="sxs-lookup"><span data-stu-id="180ac-120">Category</span></span>

<span data-ttu-id="180ac-121">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="180ac-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="180ac-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="180ac-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
