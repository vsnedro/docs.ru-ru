---
title: Тестирование библиотеки классов .NET Standard с помощью .NET Core и Visual Studio
description: Создайте проект модульного теста для библиотеки классов .NET Core. Проверьте правильность работы библиотеки классов .NET Core с помощью модульных тестов.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: f20b089fd22794d5aaeff34502e960fe41a565e1
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "84700973"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="f88a3-104">Учебник. Тестирование библиотеки классов .NET Standard с помощью .NET Core и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f88a3-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="f88a3-105">В этом руководстве показано, как автоматизировать модульное тестирование путем добавления тестового проекта в решение.</span><span class="sxs-lookup"><span data-stu-id="f88a3-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f88a3-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f88a3-106">Prerequisites</span></span>

- <span data-ttu-id="f88a3-107">В этом руководстве используется решение, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f88a3-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="f88a3-108">Создание проекта модульного теста</span><span class="sxs-lookup"><span data-stu-id="f88a3-108">Create a unit test project</span></span>

<span data-ttu-id="f88a3-109">Модульные тесты обеспечивают автоматическое тестирование программного обеспечения во время разработки и публикации.</span><span class="sxs-lookup"><span data-stu-id="f88a3-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="f88a3-110">[MSTest](https://github.com/Microsoft/testfx-docs) — это одна из трех доступных для выбора платформ тестирования.</span><span class="sxs-lookup"><span data-stu-id="f88a3-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="f88a3-111">Другими являются [xUnit](https://xunit.net/) и [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="f88a3-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="f88a3-112">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f88a3-112">Start Visual Studio.</span></span>

1. <span data-ttu-id="f88a3-113">Откройте решение`ClassLibraryProjects`, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f88a3-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="f88a3-114">Добавьте в решение новый проект модульного теста с именем StringLibraryTest.</span><span class="sxs-lookup"><span data-stu-id="f88a3-114">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="f88a3-115">Щелкните решение в **обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-115">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="f88a3-116">На странице **Добавить новый проект** введите в поле поиска **mstest**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-116">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="f88a3-117">Выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="f88a3-117">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="f88a3-118">Выберите шаблон **Тестовый проект MSTest (.NET Core)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-118">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="f88a3-119">На странице **Настроить новый проект** введите **StringLibraryTest** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-119">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="f88a3-120">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-120">Then choose **Create**.</span></span>

1. <span data-ttu-id="f88a3-121">Visual Studio создаст проект и откроет файл класса в окне кода с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="f88a3-121">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="f88a3-122">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="f88a3-122">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   <span data-ttu-id="f88a3-123">Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f88a3-123">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="f88a3-124">Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="f88a3-124">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="f88a3-125">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> к классу `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="f88a3-126">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> для определения `TestMethod1` в C# или `TestSub` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f88a3-126">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="f88a3-127">При запуске модульного теста автоматически выполняются все методы теста, помеченные атрибутом [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), в тестовом классе, помеченном атрибутом [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute).</span><span class="sxs-lookup"><span data-stu-id="f88a3-127">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="f88a3-128">Добавление ссылки на проект</span><span class="sxs-lookup"><span data-stu-id="f88a3-128">Add a project reference</span></span>

<span data-ttu-id="f88a3-129">Чтобы тестовый проект работал с классом `StringLibrary`, добавьте в проект **StringLibraryTest** ссылку на проект `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-129">For the test project to work with the `StringLibrary` class, add a reference in the **StringLibraryTest** project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="f88a3-130">В **обозревателе решений** правой кнопкой мыши щелкните узел **Зависимости** в проекте **StringLibraryTest** и в контекстном меню выберите пункт **Добавить ссылку на проект**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-130">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="f88a3-131">В диалоговом окне **Диспетчер ссылок** разверните узел **Проекты** и установите флажок рядом с пунктом **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-131">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="f88a3-132">Добавление ссылки на сборку `StringLibrary` позволяет компилятору находить методы **StringLibrary** во время компиляции проекта **StringLibraryTest**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-132">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="f88a3-133">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-133">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="f88a3-134">Добавление и выполнение методов модульного теста</span><span class="sxs-lookup"><span data-stu-id="f88a3-134">Add and run unit test methods</span></span>

<span data-ttu-id="f88a3-135">При запуске модульного теста Visual Studio выполняет каждый метод, помеченный атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>, в классе, помеченном атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f88a3-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="f88a3-136">Метод теста завершается, когда происходит первый сбой или когда все тесты, содержащиеся в методе, будут успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="f88a3-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="f88a3-137">В самых распространенных тестах вызываются члены класса <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="f88a3-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="f88a3-138">Многие методы утверждения (Assert) принимают по крайней мере два параметра, из которых один представляет ожидаемый результат теста, а второй — фактический результат теста.</span><span class="sxs-lookup"><span data-stu-id="f88a3-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="f88a3-139">Наиболее популярные из этих методов класса `Assert` перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="f88a3-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="f88a3-140">Методы утверждения</span><span class="sxs-lookup"><span data-stu-id="f88a3-140">Assert methods</span></span>     | <span data-ttu-id="f88a3-141">Функция</span><span class="sxs-lookup"><span data-stu-id="f88a3-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="f88a3-142">Проверяет равенство двух значений или объектов.</span><span class="sxs-lookup"><span data-stu-id="f88a3-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="f88a3-143">Утверждение не выполняется, если значения или объекты не равны.</span><span class="sxs-lookup"><span data-stu-id="f88a3-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="f88a3-144">Проверяет, что две объектные переменные ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="f88a3-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="f88a3-145">Утверждение не выполняется, если переменные ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="f88a3-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="f88a3-146">Проверяет, что условие имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="f88a3-147">Утверждение не выполняется, если условие имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="f88a3-148">Проверяет, что объект не имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="f88a3-149">Утверждение не выполняется, если объект является `null`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="f88a3-150">Вы можете также использовать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> в методе теста, чтобы указать тип исключения, которое он должен создавать.</span><span class="sxs-lookup"><span data-stu-id="f88a3-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="f88a3-151">Такой тест считается не выполненным, если заявленное исключение не было создано.</span><span class="sxs-lookup"><span data-stu-id="f88a3-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="f88a3-152">Для тестирования метода `StringLibrary.StartsWithUpper` необходимо предоставить несколько строк, которые начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f88a3-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="f88a3-153">Предполагается, что в этих случаях метод возвратит `true`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f88a3-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f88a3-154">Представьте также несколько строк, которые не начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f88a3-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="f88a3-155">Предполагается, что в этих случаях метод возвратит `false`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f88a3-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f88a3-156">Так как ваш метод библиотеки обрабатывает строки, нам нужно проверить правильность обработки [пустых строк (`String.Empty`)](xref:System.String.Empty) (так называется допустимая строка, которая не содержит символов и для которой свойство <xref:System.String.Length> имеет значение 0) и строки `null`, которая не была инициализирована.</span><span class="sxs-lookup"><span data-stu-id="f88a3-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="f88a3-157">Метод `StartsWithUpper` можно вызвать напрямую как статический метод и передать ему один аргумент типа <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f88a3-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="f88a3-158">Или метод `StartsWithUpper` можно вызвать как метод расширения для переменной `string`, которой назначено значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="f88a3-159">Вы определите три метода, каждый из которых вызывает метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> для каждого элемента в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="f88a3-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="f88a3-160">Вы вызовете перегруженную версию метода, которая позволяет указать сообщение об ошибке, отображаемое в случае сбоя теста.</span><span class="sxs-lookup"><span data-stu-id="f88a3-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="f88a3-161">В этом сообщении определяется строка, вызвавшая сбой.</span><span class="sxs-lookup"><span data-stu-id="f88a3-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="f88a3-162">Создание методов теста:</span><span class="sxs-lookup"><span data-stu-id="f88a3-162">To create the test methods:</span></span>

1. <span data-ttu-id="f88a3-163">В окне кода *UnitTest1.cs* или *UnitTest1.vb* замените отображаемый код на следующий текст:</span><span class="sxs-lookup"><span data-stu-id="f88a3-163">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="f88a3-164">Тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C).</span><span class="sxs-lookup"><span data-stu-id="f88a3-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="f88a3-165">Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).</span><span class="sxs-lookup"><span data-stu-id="f88a3-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="f88a3-166">В строке меню выберите **Файл** > **Сохранить UnitTest1.cs как** или **Файл** > **Сохранить UnitTest1.vb как**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-166">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="f88a3-167">В диалоговом окне **Сохранить файл как** щелкните стрелку рядом с кнопкой **Сохранить** и выберите вариант **Сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-167">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-168">![Диалоговое окно "Сохранить файл как" в Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-168">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="f88a3-169">В диалоговом окне **Подтверждение сохранения** нажмите кнопку **Да**, чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="f88a3-169">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="f88a3-170">В диалоговом окне **Дополнительные параметры сохранения** выберите в раскрывающемся списка **Кодировка** вариант **Юникод (UTF-8, с сигнатурой), кодовая страница 65001** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-170">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-171">![Диалоговое окно "Дополнительные параметры сохранения" в Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-171">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="f88a3-172">Если вы не сохраните исходный код в кодировке UTF8, Visual Studio может сохранить его как файл ASCII.</span><span class="sxs-lookup"><span data-stu-id="f88a3-172">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="f88a3-173">В этом случае среде выполнения не удастся правильно раскодировать символы UTF8 за пределами стандартного диапазона ASCII, и результаты теста будут неправильными.</span><span class="sxs-lookup"><span data-stu-id="f88a3-173">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="f88a3-174">В строке меню выберите **Тест** > **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-174">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="f88a3-175">Если окно **обозревателя тестов** не открыто, откройте его, выбрав **Тест** > **Обозреватель тестов**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-175">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="f88a3-176">В разделе **Пройденные тесты** перечислены три теста, а раздел **Сводка** содержит результат тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="f88a3-176">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-177">![Окно "Обозреватель тестов" с пройденными тестами](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-177">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="f88a3-178">Обработка сбоев теста</span><span class="sxs-lookup"><span data-stu-id="f88a3-178">Handle test failures</span></span>

<span data-ttu-id="f88a3-179">Выполняя разработку на основе тестирования (TDD), вы сначала пишете тесты, и они завершаются сбоем при первом запуске.</span><span class="sxs-lookup"><span data-stu-id="f88a3-179">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="f88a3-180">Затем вы добавляете код в приложение, и тест успешно выполняется.</span><span class="sxs-lookup"><span data-stu-id="f88a3-180">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="f88a3-181">В рамках этого учебника вы создали тест после написания кода приложения для его проверки, поэтому тест был пройден.</span><span class="sxs-lookup"><span data-stu-id="f88a3-181">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="f88a3-182">Чтобы проверить, завершается ли тест ошибкой, как и ожидается, добавьте недопустимое значение во входные данные теста.</span><span class="sxs-lookup"><span data-stu-id="f88a3-182">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="f88a3-183">Измените массив `words` в методе `TestDoesNotStartWithUpper`, включив в него строку "Error".</span><span class="sxs-lookup"><span data-stu-id="f88a3-183">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="f88a3-184">Сохранять файл не требуется, поскольку при сборке решения для выполнения тестов Visual Studio автоматически сохраняет открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="f88a3-184">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="f88a3-185">Выполните тест, последовательно выбрав в строке меню пункты **Тест** > **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-185">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="f88a3-186">В окне **Обозреватель тестов** будет указано, что два теста выполнены успешно, а третий завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f88a3-186">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-187">![Окно "Обозреватель тестов" с тестами, которые завершились ошибкой](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-187">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="f88a3-188">Выберите непройденный тест `TestDoesNotStartWith`.</span><span class="sxs-lookup"><span data-stu-id="f88a3-188">Select the failed test, `TestDoesNotStartWith`.</span></span>

   <span data-ttu-id="f88a3-189">В окне **Обозреватель тестов** появится сообщение, созданное методом утверждения "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="f88a3-189">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="f88a3-190">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="f88a3-190">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="f88a3-191">Из-за этого сбоя строки в массиве, расположенные после слова "Error", не проверялись.</span><span class="sxs-lookup"><span data-stu-id="f88a3-191">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-192">![Окно "Обозреватель тестов" с сообщением о том, что утверждение IsFalse ошибочно](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-192">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="f88a3-193">Удалите строку "Error", которую вы добавили на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="f88a3-193">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="f88a3-194">Еще раз запустите тест. Теперь тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="f88a3-194">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="f88a3-195">Тестирование версии выпуска для библиотеки</span><span class="sxs-lookup"><span data-stu-id="f88a3-195">Test the Release version of the library</span></span>

<span data-ttu-id="f88a3-196">Теперь, когда все тесты пройдены при выполнении сборки в режиме отладки, следует запустить все тесты еще раз, теперь уже для сборки библиотеки в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="f88a3-196">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="f88a3-197">Некоторые факторы, например оптимизации компилятора, иногда могут вызывать разное поведение сборки в режимах отладки и выпуска.</span><span class="sxs-lookup"><span data-stu-id="f88a3-197">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="f88a3-198">Протестируйте сборку выпуска следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f88a3-198">To test the Release build:</span></span>

1. <span data-ttu-id="f88a3-199">В панели инструментов Visual Studio измените конфигурацию сборки с режима **Отладка** на **Выпуск**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-199">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-200">![Панель инструментов Visual Studio с выделенной сборкой выпуска](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-200">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="f88a3-201">В **обозревателе решений** щелкните проект **StringLibrary** правой кнопкой мыши и выберите в контекстном меню пункт **Сборка**, чтобы выполнить повторную компиляцию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f88a3-201">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f88a3-202">![Контекстное меню проекта StringLibrary с командой сборки](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="f88a3-202">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="f88a3-203">Выполните модульные тесты, выбрав в строке меню **Тест** > **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="f88a3-203">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="f88a3-204">Все тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="f88a3-204">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f88a3-205">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f88a3-205">Additional resources</span></span>

* [<span data-ttu-id="f88a3-206">Основные сведения о модульных тестах</span><span class="sxs-lookup"><span data-stu-id="f88a3-206">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
* [<span data-ttu-id="f88a3-207">Модульное тестирование в .NET Core и .NET Standard</span><span class="sxs-lookup"><span data-stu-id="f88a3-207">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="f88a3-208">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f88a3-208">Next steps</span></span>

<span data-ttu-id="f88a3-209">В этом руководстве вы выполнили модульное тестирование библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="f88a3-209">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="f88a3-210">Чтобы сделать библиотеку доступной другим пользователям, опубликуйте ее в [NuGet](https://nuget.org) в качестве пакета.</span><span class="sxs-lookup"><span data-stu-id="f88a3-210">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="f88a3-211">Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:</span><span class="sxs-lookup"><span data-stu-id="f88a3-211">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f88a3-212">Создание и публикация пакета NuGet с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f88a3-212">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="f88a3-213">Если библиотека опубликована как пакет NuGet, ее могут устанавливать и использовать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="f88a3-213">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="f88a3-214">Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:</span><span class="sxs-lookup"><span data-stu-id="f88a3-214">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f88a3-215">Установка и использование пакета в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f88a3-215">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="f88a3-216">Библиотеку не нужно распространять как пакет.</span><span class="sxs-lookup"><span data-stu-id="f88a3-216">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="f88a3-217">Ее можно объединить с консольным приложением, где она используется.</span><span class="sxs-lookup"><span data-stu-id="f88a3-217">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="f88a3-218">Чтобы узнать, как опубликовать консольное приложение, ознакомьтесь с предыдущим руководством в этой серии:</span><span class="sxs-lookup"><span data-stu-id="f88a3-218">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f88a3-219">Публикация консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f88a3-219">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
