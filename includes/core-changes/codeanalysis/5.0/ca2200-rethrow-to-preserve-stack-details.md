---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538932"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="c5dde-101">CA2200. Повторно порождайте исключения для сохранения сведений стека</span><span class="sxs-lookup"><span data-stu-id="c5dde-101">CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="c5dde-102">Начиная с .NET 5.0 правило [CA2200](/visualstudio/code-quality/ca2200) анализатора кода .NET включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5dde-102">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="c5dde-103">Оно создает предупреждение сборки для всех блоков `catch`, которые повторно выдают исключение, а исключение явным образом указывается в операторе `throw`.</span><span class="sxs-lookup"><span data-stu-id="c5dde-103">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c5dde-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="c5dde-104">Change description</span></span>

<span data-ttu-id="c5dde-105">Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="c5dde-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="c5dde-106">Некоторые из этих правил включены по умолчанию, в том числе [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="c5dde-106">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="c5dde-107">Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.</span><span class="sxs-lookup"><span data-stu-id="c5dde-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="c5dde-108">Правило CA2200 помечает код, в котором исключения вызываются повторно, а переменная исключения указывается в операторе `throw`.</span><span class="sxs-lookup"><span data-stu-id="c5dde-108">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="c5dde-109">Часть информации в появившемся исключении представляет собой трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="c5dde-109">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="c5dde-110">Трассировка стека — это список иерархии вызовов методов, который начинается с метода, вызывающего исключение, и завершается методом, перехватывающим исключение.</span><span class="sxs-lookup"><span data-stu-id="c5dde-110">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="c5dde-111">Если исключение повторно создается заданием исключения в операторе `throw`, трассировка стека перезапускается в текущем методе, а список вызовов метода между исходным методом, создавшим исключение, и текущим методом теряется.</span><span class="sxs-lookup"><span data-stu-id="c5dde-111">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="c5dde-112">Для сохранения исходных данных трассировки стека с исключением следует использовать оператор `throw` без указания исключения.</span><span class="sxs-lookup"><span data-stu-id="c5dde-112">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="c5dde-113">Следующий фрагмент кода не создает предупреждение для правила CA2200.</span><span class="sxs-lookup"><span data-stu-id="c5dde-113">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="c5dde-114">Однако строка с комментарием *будет* вызывать нарушение.</span><span class="sxs-lookup"><span data-stu-id="c5dde-114">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a><span data-ttu-id="c5dde-115">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c5dde-115">Version introduced</span></span>

<span data-ttu-id="c5dde-116">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="c5dde-116">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c5dde-117">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="c5dde-117">Recommended action</span></span>

- <span data-ttu-id="c5dde-118">Повторно создайте исключения без явного указания исключения.</span><span class="sxs-lookup"><span data-stu-id="c5dde-118">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="c5dde-119">Дополнительные сведения см. в правиле [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="c5dde-119">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="c5dde-120">Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="c5dde-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="c5dde-121">Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="c5dde-121">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="c5dde-122">Категория</span><span class="sxs-lookup"><span data-stu-id="c5dde-122">Category</span></span>

<span data-ttu-id="c5dde-123">Анализ кода</span><span class="sxs-lookup"><span data-stu-id="c5dde-123">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c5dde-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c5dde-124">Affected APIs</span></span>

<span data-ttu-id="c5dde-125">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="c5dde-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
