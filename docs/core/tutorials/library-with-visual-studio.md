---
title: Создание библиотеки классов .NET Standard с помощью Visual Studio
description: Сведения о создании библиотеки классов .NET Standard с помощью Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 69259b1d47a8e30945c578db10c6d697c81fa261
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164406"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="e513a-103">Учебник. Создание библиотеки .NET Standard с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e513a-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="e513a-104">В этом руководстве вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="e513a-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="e513a-105">Вы реализуете его как [метод расширения](../../csharp/programming-guide/classes-and-structs/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e513a-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="e513a-106">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="e513a-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="e513a-107">Библиотеку классов, предназначенную для .NET Standard 2.0, можно вызывать из любой реализации .NET, которая поддерживает эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e513a-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="e513a-108">Когда вы завершите создание библиотеки классов, можете распространить ее как независимый компонент или включить в состав одного или нескольких пакетов приложения.</span><span class="sxs-lookup"><span data-stu-id="e513a-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e513a-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e513a-109">Prerequisites</span></span>

- <span data-ttu-id="e513a-110">[Visual Studio 2019 версии 16.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="e513a-110">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="e513a-111">Пакет SDK для .NET Core 3.1 устанавливается автоматически при выборе этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e513a-111">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="e513a-112">Дополнительные сведения см. в разделе [Установка с помощью Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) статьи [Установка пакета SDK для .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="e513a-112">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="e513a-113">Создание решения</span><span class="sxs-lookup"><span data-stu-id="e513a-113">Create a solution</span></span>

<span data-ttu-id="e513a-114">Начните с создания пустого решения для размещения проекта библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="e513a-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="e513a-115">Решение Visual Studio служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="e513a-115">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="e513a-116">Вы будете добавлять дополнительные связанные проекты в одно решение.</span><span class="sxs-lookup"><span data-stu-id="e513a-116">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="e513a-117">Чтобы создать пустое решение, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e513a-117">To create the blank solution:</span></span>

1. <span data-ttu-id="e513a-118">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e513a-118">Start Visual Studio.</span></span>

2. <span data-ttu-id="e513a-119">На начальном экране выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="e513a-119">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="e513a-120">В поле поиска на странице **Создание проекта** введите **решение**.</span><span class="sxs-lookup"><span data-stu-id="e513a-120">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="e513a-121">Выберите шаблон **Пустое решение** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e513a-121">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Шаблон пустого решения в Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="e513a-123">На странице **настройки нового проекта** введите **ClassLibraryProjects** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="e513a-123">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="e513a-124">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e513a-124">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="e513a-125">Создание проекта библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="e513a-125">Create a class library project</span></span>

1. <span data-ttu-id="e513a-126">Добавьте в решение новый проект библиотеки классов .NET Standard с именем "StringLibrary".</span><span class="sxs-lookup"><span data-stu-id="e513a-126">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="e513a-127">Щелкните решение в **обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="e513a-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="e513a-128">На странице **добавления нового проекта** введите в поле поиска **библиотека**.</span><span class="sxs-lookup"><span data-stu-id="e513a-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="e513a-129">Выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="e513a-129">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="e513a-130">Выберите шаблон **Библиотека классов (.NET Standard)** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e513a-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="e513a-131">На странице **настройки нового проекта** введите **StringLibrary** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="e513a-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="e513a-132">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e513a-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="e513a-133">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e513a-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="e513a-134">В **обозревателе решений** щелкните проект библиотеки правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e513a-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="e513a-135">В текстовом поле **Целевая платформа** указано, что целевой платформой проекта является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="e513a-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="e513a-137">Если вы используете Visual Basic, удалите текст в поле **Корневое пространство имен**.</span><span class="sxs-lookup"><span data-stu-id="e513a-137">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="e513a-139">Для каждого проекта Visual Basic автоматически создает пространство имен, соответствующее имени проекта.</span><span class="sxs-lookup"><span data-stu-id="e513a-139">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="e513a-140">В этом учебнике вы определите пространство имен верхнего уровня с помощью ключевого слова [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) в файле кода.</span><span class="sxs-lookup"><span data-stu-id="e513a-140">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="e513a-141">Замените код, отображаемый в окне кода, для *Class1.cs* или *Class1.vb* следующим текстом, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="e513a-141">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="e513a-142">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="e513a-142">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="e513a-143">Библиотека классов `UtilityLibraries.StringLibrary` содержит метод `StartsWithUpper`,</span><span class="sxs-lookup"><span data-stu-id="e513a-143">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="e513a-144">который возвращает значение <xref:System.Boolean>, указывающее, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e513a-144">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="e513a-145">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="e513a-145">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="e513a-146">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e513a-146">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="e513a-147">В строке меню выберите **Сборка** > **Собрать решение**, чтобы убедиться, что проект компилируется без ошибок.</span><span class="sxs-lookup"><span data-stu-id="e513a-147">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="e513a-148">Добавление консольного приложения в решение</span><span class="sxs-lookup"><span data-stu-id="e513a-148">Add a console app to the solution</span></span>

<span data-ttu-id="e513a-149">Добавьте консольное приложение, использующее библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="e513a-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="e513a-150">В приложении пользователю будет предложено ввести строку и сообщить, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e513a-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="e513a-151">Добавьте к решению новое консольное приложение .NET Core под названием "Демонстрация".</span><span class="sxs-lookup"><span data-stu-id="e513a-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="e513a-152">Щелкните решение в **Обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="e513a-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="e513a-153">На странице **Добавить новый проект** введите в поле поиска **консоль**.</span><span class="sxs-lookup"><span data-stu-id="e513a-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="e513a-154">Выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="e513a-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="e513a-155">Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e513a-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="e513a-156">На странице **Настроить новый проект** введите **Демонстрация** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="e513a-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="e513a-157">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e513a-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="e513a-158">В окне кода замените весь код файла *Program.cs* или *Program.vb* следующим текстом.</span><span class="sxs-lookup"><span data-stu-id="e513a-158">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="e513a-159">В этом коде используется переменная `row` для сохранения количества строк данных, записываемых в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="e513a-159">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="e513a-160">Всякий раз, когда оно достигает значения 25 или превышает его, код очищает окно консоли и отображается сообщение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e513a-160">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="e513a-161">Сама программа предлагает пользователю ввести строку.</span><span class="sxs-lookup"><span data-stu-id="e513a-161">The program prompts the user to enter a string.</span></span> <span data-ttu-id="e513a-162">Она сообщает, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e513a-162">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="e513a-163">Если пользователь нажимает клавишу <kbd>ВВОД</kbd>, не введя никакой строки, приложение завершает свою работу и окно консоли закрывается.</span><span class="sxs-lookup"><span data-stu-id="e513a-163">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="e513a-164">Добавление ссылки на проект</span><span class="sxs-lookup"><span data-stu-id="e513a-164">Add a project reference</span></span>

<span data-ttu-id="e513a-165">Изначально новый проект консольного приложения не имеет доступа к библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="e513a-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="e513a-166">Чтобы позволить приложению вызывать методы из библиотеки классов, создайте в проекте ссылку на проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="e513a-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="e513a-167">В **обозревателе решений** щелкните правой кнопкой мыши узел **Зависимости** проекта `ShowCase` и выберите команду **Добавить ссылку на проект**.</span><span class="sxs-lookup"><span data-stu-id="e513a-167">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Контекстное меню с пунктом "Добавить ссылку" в Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="e513a-169">В диалоговом окне **Диспетчер ссылок** выберите проект **StringLibrary**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e513a-169">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Диалоговое окно "Диспетчер ссылок" с выбранной StringLibrary](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="e513a-171">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="e513a-171">Run the app</span></span>

1. <span data-ttu-id="e513a-172">В окне **Обозреватель решений** щелкните правой кнопкой мыши проект **ShowCase** и выберите команду **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="e513a-172">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Контекстное меню проекта с пунктом "Назначить запускаемым проектом" в Visual Studio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="e513a-174">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>F5</kbd>, чтобы скомпилировать и запустить программу без отладки.</span><span class="sxs-lookup"><span data-stu-id="e513a-174">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![Панель инструментов проекта в Visual Studio c кнопкой отладки](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="e513a-176">Проверьте, как работает программа: вводите строки и нажимайте клавишу <kbd>ВВОД</kbd>. Чтобы выйти, нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e513a-176">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Окно консоли с запущенным демонстрационным проектом ShowCase":::

## <a name="additional-resources"></a><span data-ttu-id="e513a-178">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e513a-178">Additional resources</span></span>

* [<span data-ttu-id="e513a-179">Разработка библиотек с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="e513a-179">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="e513a-180">[Список версий .NET Standard и поддерживаемых ими платформ](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="e513a-180">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e513a-181">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e513a-181">Next steps</span></span>

<span data-ttu-id="e513a-182">В этом руководстве вы создали решение, добавили проект библиотеки и добавили проект консольного приложения, использующего библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e513a-182">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="e513a-183">В следующем руководстве вы добавите в решение проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="e513a-183">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e513a-184">Тестирование библиотеки .NET Standard с помощью .NET Core и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e513a-184">Test a .NET Standard library with .NET Core using Visual Studio</span></span>](testing-library-with-visual-studio.md)
