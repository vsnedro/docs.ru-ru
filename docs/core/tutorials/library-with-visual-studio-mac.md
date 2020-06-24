---
title: Создание библиотеки классов .NET Standard с помощью Visual Studio для Mac
description: Сведения о создании библиотеки классов .NET Standard с помощью Visual Studio для Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 3a107fff2fd6aef5e06d9af3eac334fbf5688fa5
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713421"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a><span data-ttu-id="20d9c-103">Учебник. Создание библиотеки .NET Standard с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="20d9c-103">Tutorial: Create a .NET Standard library using Visual Studio for Mac</span></span>

<span data-ttu-id="20d9c-104">В этом учебнике вы создадите простую библиотеку классов с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="20d9c-104">In this tutorial, you create a simple class library that contains a single string-handling method.</span></span> <span data-ttu-id="20d9c-105">Вы реализуете его как [метод расширения](../../csharp/programming-guide/classes-and-structs/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="20d9c-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="20d9c-106">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="20d9c-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="20d9c-107">Библиотеку классов, предназначенную для .NET Standard 2.1, может использовать приложение для любой реализации .NET, которая поддерживает версию .NET Standard 2.1.</span><span class="sxs-lookup"><span data-stu-id="20d9c-107">A class library that targets .NET Standard 2.1 can be used by an application that targets any .NET implementation that supports version 2.1 of .NET Standard.</span></span> <span data-ttu-id="20d9c-108">Когда вы завершите создание библиотеки классов, можете распространить ее как независимый компонент или включить в состав одного или нескольких пакетов приложения.</span><span class="sxs-lookup"><span data-stu-id="20d9c-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="20d9c-109">Ваш отзыв очень важен.</span><span class="sxs-lookup"><span data-stu-id="20d9c-109">Your feedback is highly valued.</span></span> <span data-ttu-id="20d9c-110">Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами.</span><span class="sxs-lookup"><span data-stu-id="20d9c-110">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="20d9c-111">В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="20d9c-111">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="20d9c-112">Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/41/index.html).</span><span class="sxs-lookup"><span data-stu-id="20d9c-112">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> - <span data-ttu-id="20d9c-113">Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом откроется [веб-страница сообщества разработчиков Visual Studio для Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="20d9c-113">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20d9c-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="20d9c-114">Prerequisites</span></span>

* <span data-ttu-id="20d9c-115">[Установите Visual Studio для Mac 8.6 или более поздней версии](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="20d9c-115">[Install Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="20d9c-116">Выберите вариант установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="20d9c-116">Select the option to install .NET Core.</span></span> <span data-ttu-id="20d9c-117">Установка Xamarin является необязательным шагом для разработки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="20d9c-117">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="20d9c-118">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="20d9c-118">For more information, see the following resources:</span></span>

  * <span data-ttu-id="20d9c-119">[Учебник. Установка Visual Studio для Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="20d9c-119">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="20d9c-120">[Поддерживаемые версии macOS](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="20d9c-120">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="20d9c-121">[Версии .NET Core, поддерживаемые Visual Studio для Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="20d9c-121">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-a-solution-with-a-class-library-project"></a><span data-ttu-id="20d9c-122">Создание решения с помощью проекта библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="20d9c-122">Create a solution with a class library project</span></span>

<span data-ttu-id="20d9c-123">Решение Visual Studio служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="20d9c-123">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="20d9c-124">Создайте решение и проект библиотеки классов в решении.</span><span class="sxs-lookup"><span data-stu-id="20d9c-124">Create a solution and a class library project in the solution.</span></span> <span data-ttu-id="20d9c-125">Позже вы добавите дополнительные связанные проекты в одно решение.</span><span class="sxs-lookup"><span data-stu-id="20d9c-125">You'll add additional, related projects to the same solution later.</span></span>

1. <span data-ttu-id="20d9c-126">Запустите Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="20d9c-126">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="20d9c-127">В окне запуска выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-127">In the start window, select **New Project**.</span></span>

1. <span data-ttu-id="20d9c-128">В узле **Многоплатформенность** диалогового окна **Создание проекта** выберите **Библиотека**, а затем — шаблон **Библиотека .NET Standard** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-128">In the **New Project** dialog under the **Multi-Platform** node, select **Library**, then select the **.NET Standard Library** template, and select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Диалоговое окно "Новый проект"":::

1. <span data-ttu-id="20d9c-130">В диалоговом окне **Configure your new .NET Standard Library** (Настройка новой библиотеки .NET Standard) выберите ".NET Standard 2.1", а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-130">In the **Configure your new .NET Standard Library** dialog, choose ".NET Standard 2.1", and select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text="Выбор .NET Standard 2.1":::

1. <span data-ttu-id="20d9c-132">Присвойте проекту имя StringLibrary, а решению — ClassLibraryProjects.</span><span class="sxs-lookup"><span data-stu-id="20d9c-132">Name the project "StringLibrary" and the solution "ClassLibraryProjects".</span></span> <span data-ttu-id="20d9c-133">Оставьте флажок **Создайте каталог проекта в каталоге решения** установленным.</span><span class="sxs-lookup"><span data-stu-id="20d9c-133">Leave **Create a project directory within the solution directory** selected.</span></span> <span data-ttu-id="20d9c-134">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-134">Select **Create**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Параметры диалогового окна "Создание проекта" Visual Studio для Mac":::

1. <span data-ttu-id="20d9c-136">В главном меню выберите **Вид** > **Панели** > **Решение** и щелкните значок закрепления, чтобы панель была открытой.</span><span class="sxs-lookup"><span data-stu-id="20d9c-136">From the main menu, select **View** > **Pads** > **Solution**, and select the dock icon to keep the pad open.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Значок закрепления для панели решения":::

1. <span data-ttu-id="20d9c-138">На панели **Решение** разверните узел `StringLibrary`, чтобы отобразить предоставленный шаблоном файл класса *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="20d9c-138">In the **Solution** pad, expand the `StringLibrary` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="20d9c-139">Удерживая нажатой клавишу <kbd>CTRL</kbd>, щелкните файл, выберите **Переименовать** в контекстном меню и переименуйте файл в *StringLibrary.cs*.</span><span class="sxs-lookup"><span data-stu-id="20d9c-139"><kbd>ctrl</kbd>-click the file, select **Rename** from the context menu, and rename the file to *StringLibrary.cs*.</span></span> <span data-ttu-id="20d9c-140">Откройте файл и замените его содержимое на следующий код:</span><span class="sxs-lookup"><span data-stu-id="20d9c-140">Open the file and replace the contents with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <span data-ttu-id="20d9c-141">Нажмите <kbd>⌘</kbd><kbd>S</kbd> (<kbd>Command</kbd>+<kbd>S</kbd>), чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="20d9c-141">Press <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) to save the file.</span></span>

1. <span data-ttu-id="20d9c-142">Выберите **Ошибки** в нижней части окна интегрированной среды разработки, чтобы открыть панель **Ошибки**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-142">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="20d9c-143">Нажмите кнопку **Выходные данные сборки**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-143">Select the **Build Output** button.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Нижнее поле окна интегрированной среды разработки Visual Studio для Mac с кнопкой "Ошибки"":::

1. <span data-ttu-id="20d9c-145">Выберите в меню **Сборка** > **Собрать все**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-145">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="20d9c-146">Выполняется сборка решения.</span><span class="sxs-lookup"><span data-stu-id="20d9c-146">The solution builds.</span></span> <span data-ttu-id="20d9c-147">На панели выходных данных отображается сообщение об успешной сборке.</span><span class="sxs-lookup"><span data-stu-id="20d9c-147">The build output panel shows that the build is successful.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Область выходных данных Visual Studio для Mac на панели "Ошибки" c сообщением об успешной сборке":::

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="20d9c-149">Добавление консольного приложения в решение</span><span class="sxs-lookup"><span data-stu-id="20d9c-149">Add a console app to the solution</span></span>

<span data-ttu-id="20d9c-150">Добавьте консольное приложение, использующее библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="20d9c-150">Add a console application that uses the class library.</span></span> <span data-ttu-id="20d9c-151">В приложении пользователю будет предложено ввести строку и сообщить, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="20d9c-151">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="20d9c-152">На панели **Решение** щелкните решение `ClassLibraryProjects` при нажатой клавише <kbd>CTRL</kbd>.</span><span class="sxs-lookup"><span data-stu-id="20d9c-152">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution.</span></span> <span data-ttu-id="20d9c-153">Добавьте новый проект **Консольное приложение**, выбрав шаблон в области **Web and Console** (Интернет и консоль) > **Приложение**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-153">Add a new **Console Application** project by selecting the template from the **Web and Console** > **App** templates, and select **Next**.</span></span>

1. <span data-ttu-id="20d9c-154">Выберите **.NET Core 3.1** в качестве **требуемой версии .NET Framework**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-154">Select **.NET Core 3.1** as the **Target Framework** and select **Next**.</span></span>

1. <span data-ttu-id="20d9c-155">Назовите проект **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-155">Name the project **ShowCase**.</span></span> <span data-ttu-id="20d9c-156">Выберите **Создать**, чтобы создать проект в решении.</span><span class="sxs-lookup"><span data-stu-id="20d9c-156">Select **Create** to create the project in the solution.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Добавление проекта ShowCase":::

1. <span data-ttu-id="20d9c-158">Откройте файл *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="20d9c-158">Open the *Program.cs* file.</span></span> <span data-ttu-id="20d9c-159">Замените код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="20d9c-159">Replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="20d9c-160">Сама программа предлагает пользователю ввести строку.</span><span class="sxs-lookup"><span data-stu-id="20d9c-160">The program prompts the user to enter a string.</span></span> <span data-ttu-id="20d9c-161">Она сообщает, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="20d9c-161">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="20d9c-162">Если пользователь нажимает клавишу <kbd>ВВОД</kbd>, не введя никакой строки, приложение завершает свою работу и окно консоли закрывается.</span><span class="sxs-lookup"><span data-stu-id="20d9c-162">If the user presses the <kbd>enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

   <span data-ttu-id="20d9c-163">В этом коде используется переменная `row` для сохранения количества строк данных, записываемых в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="20d9c-163">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="20d9c-164">Всякий раз, когда оно достигает значения 25 или превышает его, код очищает окно консоли и отображается сообщение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="20d9c-164">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="20d9c-165">Добавление ссылки на проект</span><span class="sxs-lookup"><span data-stu-id="20d9c-165">Add a project reference</span></span>

<span data-ttu-id="20d9c-166">Изначально новый проект консольного приложения не имеет доступа к библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="20d9c-166">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="20d9c-167">Чтобы позволить приложению вызывать методы из библиотеки классов, создайте в проекте ссылку на проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="20d9c-167">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="20d9c-168">На панели **Решения**, удерживая нажатой клавишу <kbd>CTRL</kbd>, щелкните узел **Зависимости** нового проекта **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-168">In the **Solutions** pad, <kbd>ctrl</kbd>-click the **Dependencies** node of the new **ShowCase** project.</span></span> <span data-ttu-id="20d9c-169">В контекстном меню выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-169">In the context menu, select **Add Reference**.</span></span>

1. <span data-ttu-id="20d9c-170">В диалоговом окне **Ссылки** выберите проект **StringLibrary** и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d9c-170">In the **References** dialog, select **StringLibrary** and select **OK**.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="20d9c-171">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="20d9c-171">Run the app</span></span>

1. <span data-ttu-id="20d9c-172">Удерживая нажатой клавишу <kbd>CTRL</kbd>, щелкните проект ShowCase и выберите **Запустить проект** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="20d9c-172"><kbd>ctrl</kbd>-click on the ShowCase project and select **Run project** from the context menu.</span></span>

1. <span data-ttu-id="20d9c-173">Проверьте, как работает программа: вводите строки и нажимайте клавишу <kbd>ВВОД</kbd>. Чтобы выйти, просто нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="20d9c-173">Try out the program by entering strings and pressing <kbd>enter</kbd>, then press <kbd>enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Окно консоли Visual Studio для Mac с отображением запуска приложения":::

## <a name="additional-resources"></a><span data-ttu-id="20d9c-175">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="20d9c-175">Additional resources</span></span>

* [<span data-ttu-id="20d9c-176">Разработка библиотек с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="20d9c-176">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="20d9c-177">[Список версий .NET Standard и поддерживаемых ими платформ](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="20d9c-177">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>
* [<span data-ttu-id="20d9c-178">Заметки о выпуске Visual Studio 2019 для Mac</span><span class="sxs-lookup"><span data-stu-id="20d9c-178">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a><span data-ttu-id="20d9c-179">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="20d9c-179">Next steps</span></span>

<span data-ttu-id="20d9c-180">В этом учебнике вы создали решение и проект библиотеки, а также добавили проект консольного приложения, использующего эту библиотеку.</span><span class="sxs-lookup"><span data-stu-id="20d9c-180">In this tutorial, you created a solution and a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="20d9c-181">В следующем руководстве вы добавите в решение проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="20d9c-181">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="20d9c-182">Тестирование библиотеки .NET Standard с помощью .NET Core и Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="20d9c-182">Test a .NET Standard library with .NET Core using Visual Studio for Mac</span></span>](testing-library-with-visual-studio-mac.md)
