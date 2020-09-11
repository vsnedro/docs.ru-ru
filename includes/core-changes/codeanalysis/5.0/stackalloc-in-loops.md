---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465594"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="012f8-101">CA2014: не используйте stackalloc в циклах</span><span class="sxs-lookup"><span data-stu-id="012f8-101">CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="012f8-102">Правило [CA2014](/visualstudio/code-quality/ca2014) анализатора кода .NET включено по умолчанию, начиная с .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="012f8-102">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="012f8-103">Оно создает предупреждение сборки для любого кода C#, в котором используется выражение [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) внутри цикла.</span><span class="sxs-lookup"><span data-stu-id="012f8-103">It produces a build warning for any C# code where a [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

#### <a name="change-description"></a><span data-ttu-id="012f8-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="012f8-104">Change description</span></span>

<span data-ttu-id="012f8-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="012f8-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="012f8-106">Некоторые из этих правил включены по умолчанию, в том числе [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="012f8-106">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="012f8-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="012f8-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="012f8-108">Правило CA2014 ищет код C#, в котором выражение [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) используется внутри цикла.</span><span class="sxs-lookup"><span data-stu-id="012f8-108">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../docs/csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="012f8-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) выделяет память из текущего кадра стека.</span><span class="sxs-lookup"><span data-stu-id="012f8-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="012f8-110">Память не освобождается до тех пор, пока не будет возвращен текущий вызов метода, что может привести к переполнению стека.</span><span class="sxs-lookup"><span data-stu-id="012f8-110">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="012f8-111">Так как вы не можете перехватывать исключения переполнения стека, в таком случае работа приложения будет завершена.</span><span class="sxs-lookup"><span data-stu-id="012f8-111">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="012f8-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="012f8-112">Version introduced</span></span>

<span data-ttu-id="012f8-113">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="012f8-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="012f8-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="012f8-114">Recommended action</span></span>

- <span data-ttu-id="012f8-115">Старайтесь не использовать [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) в циклах.</span><span class="sxs-lookup"><span data-stu-id="012f8-115">Avoid using [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="012f8-116">Выделяйте блок памяти за пределами цикла и используйте его повторно внутри цикла.</span><span class="sxs-lookup"><span data-stu-id="012f8-116">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="012f8-117">См. раздел [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="012f8-117">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="012f8-118">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="012f8-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="012f8-119">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="012f8-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="012f8-120">Категория</span><span class="sxs-lookup"><span data-stu-id="012f8-120">Category</span></span>

<span data-ttu-id="012f8-121">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="012f8-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="012f8-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="012f8-122">Affected APIs</span></span>

<span data-ttu-id="012f8-123">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="012f8-123">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
