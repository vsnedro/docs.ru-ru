---
title: Создание библиотеки классов .NET с помощью Visual Studio Code
description: Сведения о создании библиотеки классов .NET с помощью Visual Studio Code.
ms.date: 11/18/2020
ms.openlocfilehash: 4daa077fc54da3de2f808d831e06ee5f9bb3bde7
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916095"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="f70df-103">Учебник. Создание библиотеки классов .NET с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f70df-103">Tutorial: Create a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="f70df-104">В этом руководстве вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="f70df-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span>

<span data-ttu-id="f70df-105">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="f70df-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="f70df-106">Если библиотека предназначена для .NET Standard 2.0, она может быть вызвана любой реализацией .NET (включая .NET Framework), которая поддерживает .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="f70df-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="f70df-107">Если библиотека предназначена для .NET 5, ее можно вызвать с помощью любого приложения, предназначенного для .NET 5.</span><span class="sxs-lookup"><span data-stu-id="f70df-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="f70df-108">В этом учебнике показано, как ориентироваться на .NET 5.</span><span class="sxs-lookup"><span data-stu-id="f70df-108">This tutorial shows how to target .NET 5.</span></span>

<span data-ttu-id="f70df-109">После создания библиотеки классов ее можно распространить как независимый компонент или включить в состав одного или нескольких пакетов приложения.</span><span class="sxs-lookup"><span data-stu-id="f70df-109">When you create a class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f70df-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f70df-110">Prerequisites</span></span>

1. <span data-ttu-id="f70df-111">Установленная платформа [Visual Studio Code](https://code.visualstudio.com/) с [расширением C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="f70df-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="f70df-112">См. сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="f70df-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="f70df-113">[Пакет SDK для .NET 5.0 или более поздней версии](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="f70df-113">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="f70df-114">Создание решения</span><span class="sxs-lookup"><span data-stu-id="f70df-114">Create a solution</span></span>

<span data-ttu-id="f70df-115">Начните с создания пустого решения для размещения проекта библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="f70df-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="f70df-116">Решение служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="f70df-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="f70df-117">Вы будете добавлять дополнительные связанные проекты в одно решение.</span><span class="sxs-lookup"><span data-stu-id="f70df-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="f70df-118">Запустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f70df-118">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="f70df-119">В главном меню выберите **Файл** > **Открыть папку** (в macOS щелкните **Открыть...** ).</span><span class="sxs-lookup"><span data-stu-id="f70df-119">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="f70df-120">В диалоговом окне **Открыть папку** создайте папку *ClassLibraryProjects* и щелкните **Выбор папки** (в macOS щелкните **Открыть**).</span><span class="sxs-lookup"><span data-stu-id="f70df-120">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="f70df-121">Откройте **терминал** в Visual Studio Code, выбрав в основном меню пункт **Вид** > **Терминал**.</span><span class="sxs-lookup"><span data-stu-id="f70df-121">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="f70df-122">Откроется окно **Терминал** с командной строкой в папке *ClassLibraryProjects*.</span><span class="sxs-lookup"><span data-stu-id="f70df-122">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="f70df-123">В **окне терминала** введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f70df-123">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="f70df-124">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-124">The terminal output looks like the following example:</span></span>

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="f70df-125">Создание проекта библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="f70df-125">Create a class library project</span></span>

<span data-ttu-id="f70df-126">Добавьте в решение новый проект библиотеки классов .NET с именем "StringLibrary".</span><span class="sxs-lookup"><span data-stu-id="f70df-126">Add a new .NET class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="f70df-127">В терминале выполните следующую команду, чтобы создать проект библиотеки классов:</span><span class="sxs-lookup"><span data-stu-id="f70df-127">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="f70df-128">Команда `-o` или `--output` задает расположение для размещения созданных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f70df-128">The `-o` or `--output` command specifies the location to place the generated output.</span></span>

   <span data-ttu-id="f70df-129">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-129">The terminal output looks like the following example:</span></span>

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="f70df-130">Чтобы добавить проект библиотеки в решение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f70df-130">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="f70df-131">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-131">The terminal output looks like the following example:</span></span>

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="f70df-132">Убедитесь, что библиотека предназначена для .NET 5.</span><span class="sxs-lookup"><span data-stu-id="f70df-132">Check to make sure that the library targets .NET 5.</span></span> <span data-ttu-id="f70df-133">В **обозревателе** откройте файл *StringLibrary/StringLibrary.csproj*.</span><span class="sxs-lookup"><span data-stu-id="f70df-133">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="f70df-134">Элемент `TargetFramework` показывает, что проект предназначен для .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="f70df-134">The `TargetFramework` element shows that the project targets .NET 5.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>net5.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="f70df-135">Откройте файл *Class1.cs* и замените его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f70df-135">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="f70df-136">Библиотека классов `UtilityLibraries.StringLibrary` содержит метод `StartsWithUpper`,</span><span class="sxs-lookup"><span data-stu-id="f70df-136">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="f70df-137">который возвращает значение <xref:System.Boolean>, указывающее, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f70df-137">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="f70df-138">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="f70df-138">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="f70df-139">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f70df-139">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="f70df-140">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="f70df-140">Save the file.</span></span>

1. <span data-ttu-id="f70df-141">Выполните следующую команду, чтобы выполнить сборку решения и убедиться, что проект компилируется без ошибок.</span><span class="sxs-lookup"><span data-stu-id="f70df-141">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="f70df-142">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-142">The terminal output looks like the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\net5.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="f70df-143">Добавление консольного приложения в решение</span><span class="sxs-lookup"><span data-stu-id="f70df-143">Add a console app to the solution</span></span>

<span data-ttu-id="f70df-144">Добавьте консольное приложение, использующее библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="f70df-144">Add a console application that uses the class library.</span></span> <span data-ttu-id="f70df-145">В приложении пользователю будет предложено ввести строку и сообщить, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f70df-145">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="f70df-146">В терминале выполните следующую команду, чтобы создать проект консольного приложения:</span><span class="sxs-lookup"><span data-stu-id="f70df-146">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="f70df-147">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-147">The terminal output looks like the following example:</span></span>

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="f70df-148">Чтобы добавить проект консольного приложения в решение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f70df-148">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="f70df-149">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-149">The terminal output looks like the following example:</span></span>

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="f70df-150">Откройте файл *ShowCase/Program.cs* и замените все его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f70df-150">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="f70df-151">В этом коде используется переменная `row` для сохранения количества строк данных, записываемых в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="f70df-151">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="f70df-152">Всякий раз, когда оно достигает значения 25 или превышает его, код очищает окно консоли и отображается сообщение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f70df-152">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="f70df-153">Сама программа предлагает пользователю ввести строку.</span><span class="sxs-lookup"><span data-stu-id="f70df-153">The program prompts the user to enter a string.</span></span> <span data-ttu-id="f70df-154">Она сообщает, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f70df-154">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="f70df-155">Если пользователь нажимает клавишу <kbd>ВВОД</kbd>, не введя никакой строки, приложение завершает свою работу и окно консоли закрывается.</span><span class="sxs-lookup"><span data-stu-id="f70df-155">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="f70df-156">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="f70df-156">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="f70df-157">Добавление ссылки на проект</span><span class="sxs-lookup"><span data-stu-id="f70df-157">Add a project reference</span></span>

<span data-ttu-id="f70df-158">Изначально новый проект консольного приложения не имеет доступа к библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="f70df-158">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="f70df-159">Чтобы позволить приложению вызывать методы из библиотеки классов, создайте в проекте ссылку на проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="f70df-159">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="f70df-160">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f70df-160">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="f70df-161">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-161">The terminal output looks like the following example:</span></span>

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="f70df-162">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="f70df-162">Run the app</span></span>

1. <span data-ttu-id="f70df-163">Выполните следующую команду в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="f70df-163">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="f70df-164">Проверьте, как работает программа: вводите строки и нажимайте клавишу <kbd>ВВОД</kbd>. Чтобы выйти, нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f70df-164">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="f70df-165">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f70df-165">The terminal output looks like the following example:</span></span>

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a><span data-ttu-id="f70df-166">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f70df-166">Additional resources</span></span>

* [<span data-ttu-id="f70df-167">Разработка библиотек с помощью .NET CLI</span><span class="sxs-lookup"><span data-stu-id="f70df-167">Develop libraries with the .NET CLI</span></span>](libraries.md)

## <a name="next-steps"></a><span data-ttu-id="f70df-168">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f70df-168">Next steps</span></span>

<span data-ttu-id="f70df-169">В этом руководстве вы создали решение, добавили проект библиотеки и добавили проект консольного приложения, использующего библиотеку.</span><span class="sxs-lookup"><span data-stu-id="f70df-169">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="f70df-170">В следующем руководстве вы добавите в решение проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="f70df-170">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f70df-171">Тестирование библиотеки классов .NET с помощью .NET и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f70df-171">Test a .NET class library with .NET using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
