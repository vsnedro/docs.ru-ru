---
title: Выполнение выборочных модульных тестов
description: Как использовать выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test в .NET Core.
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728182"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="bb6cc-103">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="bb6cc-103">Run selective unit tests</span></span>

<span data-ttu-id="bb6cc-104">Использовать выражения фильтра для выполнения выборочных модульных тестов можно с помощью команды `dotnet test` в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="bb6cc-105">В этой статье показано, как отфильтровывать модульные тесты для выполнения.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="bb6cc-106">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="bb6cc-107">Если вы используете `vstest.console.exe`, замените `--filter` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="bb6cc-108">Экранирование символов</span><span class="sxs-lookup"><span data-stu-id="bb6cc-108">Character escaping</span></span>

<span data-ttu-id="bb6cc-109">Чтобы в `*nix` использовать фильтры, содержащие восклицательный знак (!), требуется выполнять экранирование, так как символ `!` зарезервирован.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="bb6cc-110">Например, этот фильтр пропускает все тесты, если пространство имен содержит IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="bb6cc-111">Обратите внимание на обратную косую черту перед восклицательным знаком.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="bb6cc-112">Для значений `FullyQualifiedName`, включающих запятую для параметров универсального типа, необходимо экранировать запятую с помощью `%2C`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="bb6cc-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb6cc-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="bb6cc-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="bb6cc-114">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="bb6cc-115">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-115">Expression</span></span> | <span data-ttu-id="bb6cc-116">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="bb6cc-117">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="bb6cc-118">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="bb6cc-119">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="bb6cc-120">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="bb6cc-121">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTest1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="bb6cc-122">Выполняет все тесты, за исключением `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="bb6cc-123">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="bb6cc-124">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="bb6cc-125">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="bb6cc-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bb6cc-126">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-126">Expression</span></span> | <span data-ttu-id="bb6cc-127">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="bb6cc-128">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="bb6cc-129">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bb6cc-130">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="bb6cc-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="bb6cc-131">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="bb6cc-132">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-132">Expression</span></span> | <span data-ttu-id="bb6cc-133">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="bb6cc-134">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="bb6cc-135">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="bb6cc-136">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="bb6cc-137">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="bb6cc-138">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-138">Expression</span></span> | <span data-ttu-id="bb6cc-139">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="bb6cc-140">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="bb6cc-141">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="bb6cc-142">Выполняет тесты с `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="bb6cc-143">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="bb6cc-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bb6cc-144">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-144">Expression</span></span> | <span data-ttu-id="bb6cc-145">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="bb6cc-146">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="bb6cc-147">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **и** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bb6cc-148">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **и** `Category` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="bb6cc-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="bb6cc-149">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="bb6cc-150">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-150">Expression</span></span> | <span data-ttu-id="bb6cc-151">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="bb6cc-152">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="bb6cc-153">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="bb6cc-154">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="bb6cc-155">Выполняет тесты, которые находятся в классе `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="bb6cc-156">Выполняет все тесты, за исключением `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="bb6cc-157">Выполняет тесты, которые помечены атрибутом `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="bb6cc-158">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="bb6cc-159">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="bb6cc-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bb6cc-160">Выражение</span><span class="sxs-lookup"><span data-stu-id="bb6cc-160">Expression</span></span> | <span data-ttu-id="bb6cc-161">Результат</span><span class="sxs-lookup"><span data-stu-id="bb6cc-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="bb6cc-162">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="bb6cc-163">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bb6cc-164">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="bb6cc-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="bb6cc-165">Дополнительные сведения см. в документе о [фильтре TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="bb6cc-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
