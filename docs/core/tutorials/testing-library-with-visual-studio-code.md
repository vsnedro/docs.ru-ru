---
title: Тестирование библиотеки классов .NET Standard с помощью .NET Core и Visual Studio Code
description: Создайте проект модульного теста для библиотеки классов .NET Core. Проверьте правильность работы библиотеки классов .NET Core с помощью модульных тестов.
ms.date: 06/08/2020
ms.openlocfilehash: 6ae8f6637319cd2c8c24f3e673fb6094f36b9f2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180458"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a><span data-ttu-id="116bc-104">Учебник. Тестирование библиотеки классов .NET Standard с помощью .NET Core и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="116bc-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="116bc-105">В этом руководстве показано, как автоматизировать модульное тестирование путем добавления тестового проекта в решение.</span><span class="sxs-lookup"><span data-stu-id="116bc-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="116bc-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="116bc-106">Prerequisites</span></span>

- <span data-ttu-id="116bc-107">В этом руководстве используется решение, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="116bc-107">This tutorial works with the solution that you create in [Create a .NET Standard library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="116bc-108">Создание проекта модульного теста</span><span class="sxs-lookup"><span data-stu-id="116bc-108">Create a unit test project</span></span>

<span data-ttu-id="116bc-109">Модульные тесты обеспечивают автоматическое тестирование программного обеспечения во время разработки и публикации.</span><span class="sxs-lookup"><span data-stu-id="116bc-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="116bc-110">В этом руководстве используется платформа тестирования MSTest.</span><span class="sxs-lookup"><span data-stu-id="116bc-110">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="116bc-111">[MSTest](https://github.com/Microsoft/testfx-docs) — это одна из трех доступных для выбора платформ тестирования.</span><span class="sxs-lookup"><span data-stu-id="116bc-111">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="116bc-112">Другими являются [xUnit](https://xunit.net/) и [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="116bc-112">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="116bc-113">Запустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="116bc-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="116bc-114">Откройте решение `ClassLibraryProjects`, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="116bc-114">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="116bc-115">Создайте проект модульного теста с именем StringLibraryTest.</span><span class="sxs-lookup"><span data-stu-id="116bc-115">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="116bc-116">Шаблон проекта создает файл UnitTest1.cs со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="116bc-116">The project template creates a UnitTest1.cs file with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   <span data-ttu-id="116bc-117">Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="116bc-117">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="116bc-118">Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="116bc-118">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="116bc-119">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> к классу `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="116bc-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="116bc-120">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> для определения `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="116bc-120">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="116bc-121">При запуске модульного теста автоматически выполняются все методы теста, помеченные атрибутом [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), в тестовом классе, помеченном атрибутом [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute).</span><span class="sxs-lookup"><span data-stu-id="116bc-121">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="116bc-122">Добавьте тестовый проект в решение.</span><span class="sxs-lookup"><span data-stu-id="116bc-122">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="116bc-123">Добавление ссылки на проект</span><span class="sxs-lookup"><span data-stu-id="116bc-123">Add a project reference</span></span>

<span data-ttu-id="116bc-124">Чтобы тестовый проект работал с классом `StringLibrary`, добавьте в проект `StringLibraryTest` ссылку на проект `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="116bc-124">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="116bc-125">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="116bc-125">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="116bc-126">Добавление и выполнение методов модульного теста</span><span class="sxs-lookup"><span data-stu-id="116bc-126">Add and run unit test methods</span></span>

<span data-ttu-id="116bc-127">При запуске модульного теста Visual Studio выполняет каждый метод, помеченный атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>, в классе, помеченном атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="116bc-127">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="116bc-128">Метод теста завершается, когда происходит первый сбой или когда все тесты, содержащиеся в методе, будут успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="116bc-128">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="116bc-129">В самых распространенных тестах вызываются члены класса <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="116bc-129">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="116bc-130">Многие методы утверждения (Assert) принимают по крайней мере два параметра, из которых один представляет ожидаемый результат теста, а второй — фактический результат теста.</span><span class="sxs-lookup"><span data-stu-id="116bc-130">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="116bc-131">Наиболее популярные из этих методов класса `Assert` перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="116bc-131">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="116bc-132">Методы утверждения</span><span class="sxs-lookup"><span data-stu-id="116bc-132">Assert methods</span></span>     | <span data-ttu-id="116bc-133">Функция</span><span class="sxs-lookup"><span data-stu-id="116bc-133">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="116bc-134">Проверяет равенство двух значений или объектов.</span><span class="sxs-lookup"><span data-stu-id="116bc-134">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="116bc-135">Утверждение не выполняется, если значения или объекты не равны.</span><span class="sxs-lookup"><span data-stu-id="116bc-135">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="116bc-136">Проверяет, что две объектные переменные ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="116bc-136">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="116bc-137">Утверждение не выполняется, если переменные ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="116bc-137">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="116bc-138">Проверяет, что условие имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="116bc-138">Verifies that a condition is `false`.</span></span> <span data-ttu-id="116bc-139">Утверждение не выполняется, если условие имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="116bc-139">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="116bc-140">Проверяет, что объект не имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="116bc-140">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="116bc-141">Утверждение не выполняется, если объект является `null`.</span><span class="sxs-lookup"><span data-stu-id="116bc-141">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="116bc-142">Вы можете также использовать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> в методе теста, чтобы указать тип исключения, которое он должен создавать.</span><span class="sxs-lookup"><span data-stu-id="116bc-142">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="116bc-143">Такой тест считается не выполненным, если заявленное исключение не было создано.</span><span class="sxs-lookup"><span data-stu-id="116bc-143">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="116bc-144">Для тестирования метода `StringLibrary.StartsWithUpper` необходимо предоставить несколько строк, которые начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="116bc-144">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="116bc-145">Предполагается, что в этих случаях метод возвратит `true`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="116bc-145">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="116bc-146">Представьте также несколько строк, которые не начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="116bc-146">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="116bc-147">Предполагается, что в этих случаях метод возвратит `false`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="116bc-147">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="116bc-148">Так как метод библиотеки обрабатывает строки, необходимо также убедиться, что он обрабатывает [пустую строку (`String.Empty`)](xref:System.String.Empty), а также строку `null`.</span><span class="sxs-lookup"><span data-stu-id="116bc-148">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="116bc-149">Пустая строка не содержит символов, а ее свойство <xref:System.String.Length> равно 0.</span><span class="sxs-lookup"><span data-stu-id="116bc-149">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="116bc-150">Строка `null` является неинициализированной строкой.</span><span class="sxs-lookup"><span data-stu-id="116bc-150">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="116bc-151">Метод `StartsWithUpper` можно вызвать напрямую как статический метод и передать ему один аргумент типа <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="116bc-151">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="116bc-152">Или метод `StartsWithUpper` можно вызвать как метод расширения для переменной `string`, которой назначено значение `null`.</span><span class="sxs-lookup"><span data-stu-id="116bc-152">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="116bc-153">Вы определите три метода, каждый из которых вызывает метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> для каждого элемента в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="116bc-153">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="116bc-154">Вы вызовете перегруженную версию метода, которая позволяет указать сообщение об ошибке, отображаемое в случае сбоя теста.</span><span class="sxs-lookup"><span data-stu-id="116bc-154">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="116bc-155">В этом сообщении определяется строка, вызвавшая сбой.</span><span class="sxs-lookup"><span data-stu-id="116bc-155">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="116bc-156">Создание методов теста:</span><span class="sxs-lookup"><span data-stu-id="116bc-156">To create the test methods:</span></span>

1. <span data-ttu-id="116bc-157">Откройте файл *StringLibraryTest/UnitTest1.cs* и замените все его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="116bc-157">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="116bc-158">Тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C).</span><span class="sxs-lookup"><span data-stu-id="116bc-158">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="116bc-159">Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).</span><span class="sxs-lookup"><span data-stu-id="116bc-159">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="116bc-160">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="116bc-160">Save your changes.</span></span>

1. <span data-ttu-id="116bc-161">Запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="116bc-161">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="116bc-162">В выходных данных терминала показано, что все тесты пройдены.</span><span class="sxs-lookup"><span data-stu-id="116bc-162">The terminal output shows that all tests passed.</span></span>

   ```output
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
    Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="116bc-163">Обработка сбоев теста</span><span class="sxs-lookup"><span data-stu-id="116bc-163">Handle test failures</span></span>

<span data-ttu-id="116bc-164">Выполняя разработку на основе тестирования (TDD), вы сначала пишете тесты, и они завершаются сбоем при первом запуске.</span><span class="sxs-lookup"><span data-stu-id="116bc-164">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="116bc-165">Затем вы добавляете код в приложение, и тест успешно выполняется.</span><span class="sxs-lookup"><span data-stu-id="116bc-165">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="116bc-166">В рамках этого учебника вы создали тест после написания кода приложения для его проверки, поэтому тест был пройден.</span><span class="sxs-lookup"><span data-stu-id="116bc-166">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="116bc-167">Чтобы проверить, завершается ли тест ошибкой, как и ожидается, добавьте недопустимое значение во входные данные теста.</span><span class="sxs-lookup"><span data-stu-id="116bc-167">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="116bc-168">Измените массив `words` в методе `TestDoesNotStartWithUpper`, включив в него строку "Error".</span><span class="sxs-lookup"><span data-stu-id="116bc-168">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="116bc-169">Запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="116bc-169">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="116bc-170">В выходных данных терминала показано, что один тест завершается ошибкой, и выдается сообщение об ошибке для непройденного теста. "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="116bc-170">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="116bc-171">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="116bc-171">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="116bc-172">Из-за этого сбоя строки в массиве, расположенные после слова "Error", не проверялись.</span><span class="sxs-lookup"><span data-stu-id="116bc-172">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   ```output
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
        at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper() in C:\
   Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
    Total time: 1.7825 Seconds
   ```

1. <span data-ttu-id="116bc-173">Удалите строку "Error", которую вы добавили на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="116bc-173">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="116bc-174">Еще раз запустите тест. Теперь тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="116bc-174">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="116bc-175">Тестирование версии выпуска для библиотеки</span><span class="sxs-lookup"><span data-stu-id="116bc-175">Test the Release version of the library</span></span>

<span data-ttu-id="116bc-176">Теперь, когда все тесты пройдены при выполнении сборки в режиме отладки, следует запустить все тесты еще раз, теперь уже для сборки библиотеки в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="116bc-176">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="116bc-177">Некоторые факторы, например оптимизации компилятора, иногда могут вызывать разное поведение сборки в режимах отладки и выпуска.</span><span class="sxs-lookup"><span data-stu-id="116bc-177">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="116bc-178">Запустите тесты с конфигурацией сборки "Выпуск".</span><span class="sxs-lookup"><span data-stu-id="116bc-178">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="116bc-179">Все тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="116bc-179">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="116bc-180">Отладка тестов</span><span class="sxs-lookup"><span data-stu-id="116bc-180">Debug tests</span></span>

<span data-ttu-id="116bc-181">Если в качестве IDE вы используете Visual Studio Code, то можете следовать инструкциям из руководства по [отладке консольного приложения .NET Core с помощью Visual Studio Code](debugging-with-visual-studio-code.md), чтобы выполнить отладку кода с применением проекта модульного теста.</span><span class="sxs-lookup"><span data-stu-id="116bc-181">If you're using Visual Studio Code as your IDE, you can use the same process shown in [Debug a .NET Core console application using Visual Studio Code](debugging-with-visual-studio-code.md) to debug code using your unit test project.</span></span> <span data-ttu-id="116bc-182">Вместо запуска проекта приложения *ShowCase* , откройте *StringLibraryTest/UnitTest1.cs* и выберите элемент **Выполнить все тесты** между строками 7 и 8.</span><span class="sxs-lookup"><span data-stu-id="116bc-182">Instead of starting the *ShowCase* app project, open *StringLibraryTest/UnitTest1.cs*, and select **Run All Tests** between lines 7 and 8.</span></span> <span data-ttu-id="116bc-183">Если вы не можете найти его, нажмите клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>, чтобы открыть палитру команд, и введите команду **перезагрузки окна**.</span><span class="sxs-lookup"><span data-stu-id="116bc-183">If you're unable to find it, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the command palette and enter **Reload Window**.</span></span>

<span data-ttu-id="116bc-184">Visual Studio Code запускает тестовый проект с присоединенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="116bc-184">Visual Studio Code starts the test project with the debugger attached.</span></span> <span data-ttu-id="116bc-185">Выполнение будет прервано в любой точке останова, добавленной в тестовый проект или базовый код библиотеки.</span><span class="sxs-lookup"><span data-stu-id="116bc-185">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="116bc-186">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="116bc-186">Additional resources</span></span>

* [<span data-ttu-id="116bc-187">Модульное тестирование в .NET Core и .NET Standard</span><span class="sxs-lookup"><span data-stu-id="116bc-187">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="116bc-188">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="116bc-188">Next steps</span></span>

<span data-ttu-id="116bc-189">В этом руководстве вы выполнили модульное тестирование библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="116bc-189">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="116bc-190">Чтобы сделать библиотеку доступной другим пользователям, опубликуйте ее в [NuGet](https://nuget.org) в качестве пакета.</span><span class="sxs-lookup"><span data-stu-id="116bc-190">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="116bc-191">Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:</span><span class="sxs-lookup"><span data-stu-id="116bc-191">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="116bc-192">Создание и публикация пакета с помощью CLI dotnet</span><span class="sxs-lookup"><span data-stu-id="116bc-192">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="116bc-193">Если библиотека опубликована как пакет NuGet, ее могут устанавливать и использовать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="116bc-193">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="116bc-194">Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:</span><span class="sxs-lookup"><span data-stu-id="116bc-194">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="116bc-195">Установка и использование пакета с помощью CLI dotnet</span><span class="sxs-lookup"><span data-stu-id="116bc-195">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="116bc-196">Библиотеку не нужно распространять как пакет.</span><span class="sxs-lookup"><span data-stu-id="116bc-196">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="116bc-197">Ее можно объединить с консольным приложением, где она используется.</span><span class="sxs-lookup"><span data-stu-id="116bc-197">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="116bc-198">Чтобы узнать, как опубликовать консольное приложение, ознакомьтесь с предыдущим руководством в этой серии:</span><span class="sxs-lookup"><span data-stu-id="116bc-198">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="116bc-199">Публикация консольного приложения .NET Core с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="116bc-199">Publish a .NET Core console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
