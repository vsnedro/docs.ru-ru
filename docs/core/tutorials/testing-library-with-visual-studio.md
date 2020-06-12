---
title: Тестирование библиотеки классов .NET Standard с помощью .NET Core в Visual Studio
description: Создайте проект модульного теста для библиотеки классов .NET Core. Проверьте правильность работы библиотеки классов .NET Core с помощью модульных тестов.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 48ada77b8422030fd93aa29df1df50a3ae5104fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283511"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="9cbfe-104">Учебник. Тестирование библиотеки .NET Standard с помощью .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9cbfe-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="9cbfe-105">В этом руководстве показано, как автоматизировать модульное тестирование путем добавления тестового проекта в решение.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9cbfe-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9cbfe-106">Prerequisites</span></span>

- <span data-ttu-id="9cbfe-107">В этом руководстве используется решение, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9cbfe-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="9cbfe-108">Создание проекта модульного теста</span><span class="sxs-lookup"><span data-stu-id="9cbfe-108">Create a unit test project</span></span>

1. <span data-ttu-id="9cbfe-109">Откройте решение`ClassLibraryProjects`, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9cbfe-109">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="9cbfe-110">Добавьте в решение новый проект модульного теста с именем StringLibraryTest.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-110">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="9cbfe-111">Щелкните решение в **обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-111">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="9cbfe-112">На странице **Добавить новый проект** введите в поле поиска **mstest**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-112">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="9cbfe-113">Выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-113">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="9cbfe-114">Выберите шаблон **Тестовый проект MSTest (.NET Core)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-114">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="9cbfe-115">На странице **Настроить новый проект** введите **StringLibraryTest** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-115">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="9cbfe-116">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-116">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9cbfe-117">MSTest — это одна из трех доступных для выбора платформ тестирования.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-117">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="9cbfe-118">Другими являются xUnit и nUnit.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-118">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="9cbfe-119">Visual Studio создаст проект и откроет файл класса в окне кода с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-119">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="9cbfe-120">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-120">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   <span data-ttu-id="9cbfe-121">Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-121">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="9cbfe-122">Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-122">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="9cbfe-123">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> к классу `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-123">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="9cbfe-124">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> для определения `TestMethod1` в C# или `TestSub` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="9cbfe-125">При запуске модульного теста автоматически выполняются все методы теста, помеченные атрибутом [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), в тестовом классе, помеченном атрибутом [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute).</span><span class="sxs-lookup"><span data-stu-id="9cbfe-125">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="9cbfe-126">В **обозревателе решений** правой кнопкой мыши щелкните узел **Зависимости** в проекте **StringLibraryTest** и в контекстном меню выберите пункт **Добавить ссылку на проект**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-126">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="9cbfe-127">В диалоговом окне **Диспетчер ссылок** разверните узел **Проекты** и установите флажок рядом с пунктом **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-127">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="9cbfe-128">Добавление ссылки на сборку `StringLibrary` позволяет компилятору находить методы **StringLibrary** во время компиляции проекта **StringLibraryTest**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="9cbfe-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-129">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="9cbfe-130">Добавление и выполнение методов модульного теста</span><span class="sxs-lookup"><span data-stu-id="9cbfe-130">Add and run unit test methods</span></span>

<span data-ttu-id="9cbfe-131">При запуске модульного теста Visual Studio выполняет каждый метод, помеченный атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>, в классе, помеченном атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-131">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="9cbfe-132">Метод теста завершается, когда происходит первый сбой или когда все тесты, содержащиеся в методе, будут успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-132">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="9cbfe-133">В самых распространенных тестах вызываются члены класса <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-133">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="9cbfe-134">Многие методы утверждения (Assert) принимают по крайней мере два параметра, из которых один представляет ожидаемый результат теста, а второй — фактический результат теста.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-134">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="9cbfe-135">Наиболее популярные из этих методов класса `Assert` перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-135">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="9cbfe-136">Методы утверждения</span><span class="sxs-lookup"><span data-stu-id="9cbfe-136">Assert methods</span></span>     | <span data-ttu-id="9cbfe-137">Функция</span><span class="sxs-lookup"><span data-stu-id="9cbfe-137">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="9cbfe-138">Проверяет равенство двух значений или объектов.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-138">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="9cbfe-139">Утверждение не выполняется, если значения или объекты не равны.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-139">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="9cbfe-140">Проверяет, что две объектные переменные ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-140">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="9cbfe-141">Утверждение не выполняется, если переменные ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-141">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="9cbfe-142">Проверяет, что условие имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-142">Verifies that a condition is `false`.</span></span> <span data-ttu-id="9cbfe-143">Утверждение не выполняется, если условие имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-143">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="9cbfe-144">Проверяет, что объект не имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-144">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="9cbfe-145">Утверждение не выполняется, если объект является `null`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-145">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="9cbfe-146">Вы можете также использовать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> в методе теста, чтобы указать тип исключения, которое он должен создавать.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-146">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="9cbfe-147">Такой тест считается не выполненным, если заявленное исключение не было создано.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-147">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="9cbfe-148">Для тестирования метода `StringLibrary.StartsWithUpper` необходимо предоставить несколько строк, которые начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-148">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="9cbfe-149">Предполагается, что в этих случаях метод возвратит `true`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-149">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9cbfe-150">Представьте также несколько строк, которые не начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-150">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="9cbfe-151">Предполагается, что в этих случаях метод возвратит `false`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-151">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9cbfe-152">Так как ваш метод библиотеки обрабатывает строки, нам нужно проверить правильность обработки [пустых строк (`String.Empty`)](xref:System.String.Empty) (так называется допустимая строка, которая не содержит символов и для которой свойство <xref:System.String.Length> имеет значение 0) и строки `null`, которая не была инициализирована.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-152">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="9cbfe-153">Если `StartsWithUpper` вызывается в качестве метода расширения для экземпляра <xref:System.String>, ему нельзя передавать строку `null`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-153">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="9cbfe-154">Однако его можно вызвать напрямую как статический метод и передать ему один аргумент типа <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-154">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="9cbfe-155">Вы определите три метода, каждый из которых поочередно вызывает метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> для каждого элемента в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-155">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="9cbfe-156">Так как метод теста завершается ошибкой при первом же сбое, вы вызовете перегруженную версию метода, которая позволяет передать строку и указать строковое значение, используемое в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-156">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="9cbfe-157">Создание методов теста:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-157">To create the test methods:</span></span>

1. <span data-ttu-id="9cbfe-158">В окне кода *UnitTest1.cs* или *UnitTest1.vb* замените отображаемый код на следующий текст:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-158">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="9cbfe-159">Тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C).</span><span class="sxs-lookup"><span data-stu-id="9cbfe-159">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="9cbfe-160">Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).</span><span class="sxs-lookup"><span data-stu-id="9cbfe-160">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="9cbfe-161">В строке меню выберите **Файл** > **Сохранить UnitTest1.cs как** или **Файл** > **Сохранить UnitTest1.vb как**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-161">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="9cbfe-162">В диалоговом окне **Сохранить файл как** щелкните стрелку рядом с кнопкой **Сохранить** и выберите вариант **Сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-162">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-163">![Диалоговое окно "Сохранить файл как" в Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-163">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="9cbfe-164">В диалоговом окне **Подтверждение сохранения** нажмите кнопку **Да**, чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-164">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="9cbfe-165">В диалоговом окне **Дополнительные параметры сохранения** выберите в раскрывающемся списка **Кодировка** вариант **Юникод (UTF-8, с сигнатурой), кодовая страница 65001** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-165">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-166">![Диалоговое окно "Дополнительные параметры сохранения" в Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-166">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="9cbfe-167">Если вы не сохраните исходный код в кодировке UTF8, Visual Studio может сохранить его как файл ASCII.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-167">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="9cbfe-168">В этом случае среде выполнения не удастся правильно раскодировать символы UTF8 за пределами стандартного диапазона ASCII, и результаты теста будут неправильными.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-168">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="9cbfe-169">В строке меню выберите **Тест** > **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-169">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="9cbfe-170">Если окно **обозревателя тестов** не открыто, откройте его, выбрав **Тест** > **Обозреватель тестов**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-170">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="9cbfe-171">В разделе **Пройденные тесты** перечислены три теста, а раздел **Сводка** содержит результат тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-171">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-172">![Окно "Обозреватель тестов" с пройденными тестами](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-172">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="9cbfe-173">Обработка сбоев теста</span><span class="sxs-lookup"><span data-stu-id="9cbfe-173">Handle test failures</span></span>

<span data-ttu-id="9cbfe-174">Выполняя разработку на основе тестирования (TDD), вы сначала пишете тесты, и они завершаются сбоем при первом запуске.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-174">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="9cbfe-175">Затем вы добавляете код в приложение, и тест успешно выполняется.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-175">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="9cbfe-176">В этом случае тест был создан после написания кода приложения для его проверки, поэтому тест был пройден.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-176">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="9cbfe-177">Чтобы проверить, завершается ли тест ошибкой, как и ожидается, добавьте недопустимое значение во входные данные теста.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-177">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="9cbfe-178">Измените массив `words` в методе `TestDoesNotStartWithUpper`, включив в него строку "Error".</span><span class="sxs-lookup"><span data-stu-id="9cbfe-178">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="9cbfe-179">Сохранять файл не требуется, поскольку при сборке решения для выполнения тестов Visual Studio автоматически сохраняет открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-179">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="9cbfe-180">Выполните тест, последовательно выбрав в строке меню пункты **Тест** > **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-180">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="9cbfe-181">В окне **Обозреватель тестов** будет указано, что два теста выполнены успешно, а третий завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-181">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-182">![Окно "Обозреватель тестов" с тестами, которые завершились ошибкой](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-182">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="9cbfe-183">Выберите непройденный тест `TestDoesNotStartWith`.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-183">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="9cbfe-184">В окне **Обозреватель тестов** появится сообщение, созданное методом утверждения "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-184">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="9cbfe-185">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="9cbfe-185">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="9cbfe-186">Из-за этого сбоя все строки в массиве, расположенные после слова Error, не проверялись.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-186">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-187">![Окно "Обозреватель тестов" с сообщением о том, что утверждение IsFalse ошибочно](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-187">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="9cbfe-188">Отмените изменение, которое вы внесли на шаге 1, и удалите строку "Error".</span><span class="sxs-lookup"><span data-stu-id="9cbfe-188">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="9cbfe-189">Еще раз запустите тест. Теперь тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-189">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="9cbfe-190">Тестирование версии выпуска для библиотеки</span><span class="sxs-lookup"><span data-stu-id="9cbfe-190">Test the Release version of the library</span></span>

<span data-ttu-id="9cbfe-191">Теперь, когда все тесты пройдены во время запуска версии отладки, следует запустить все тесты еще раз, теперь уже для сборки выпуска библиотеки.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-191">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="9cbfe-192">Некоторые факторы, например оптимизации компилятора, иногда могут вызывать разное поведение сборки в режимах отладки и выпуска.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="9cbfe-193">Протестируйте сборку выпуска следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-193">To test the Release build:</span></span>

1. <span data-ttu-id="9cbfe-194">В панели инструментов Visual Studio измените конфигурацию сборки с режима **Отладка** на **Выпуск**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-195">![Панель инструментов Visual Studio с выделенной сборкой выпуска](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="9cbfe-196">В **обозревателе решений** щелкните проект **StringLibrary** правой кнопкой мыши и выберите в контекстном меню пункт **Сборка**, чтобы выполнить повторную компиляцию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cbfe-197">![Контекстное меню проекта StringLibrary с командой сборки](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="9cbfe-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="9cbfe-198">Выполните модульные тесты, выбрав в строке меню **Тест** > **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-198">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="9cbfe-199">Все тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-199">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9cbfe-200">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="9cbfe-200">Additional resources</span></span>

- [<span data-ttu-id="9cbfe-201">Основные сведения о модульных тестах</span><span class="sxs-lookup"><span data-stu-id="9cbfe-201">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a><span data-ttu-id="9cbfe-202">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9cbfe-202">Next steps</span></span>

<span data-ttu-id="9cbfe-203">В этом руководстве вы выполнили модульное тестирование библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-203">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="9cbfe-204">Чтобы сделать библиотеку доступной другим пользователям, опубликуйте ее в [NuGet](https://nuget.org) в качестве пакета.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-204">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="9cbfe-205">Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-205">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9cbfe-206">Создание и публикация пакета NuGet с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9cbfe-206">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="9cbfe-207">Если библиотека опубликована как пакет NuGet, ее могут устанавливать и использовать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-207">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="9cbfe-208">Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-208">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9cbfe-209">Установка и использование пакета в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9cbfe-209">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="9cbfe-210">Библиотеку не нужно распространять как пакет.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-210">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="9cbfe-211">Ее можно объединить с консольным приложением, где она используется.</span><span class="sxs-lookup"><span data-stu-id="9cbfe-211">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="9cbfe-212">Чтобы узнать, как опубликовать консольное приложение, ознакомьтесь с предыдущим руководством в этой серии:</span><span class="sxs-lookup"><span data-stu-id="9cbfe-212">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9cbfe-213">Публикация консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9cbfe-213">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
