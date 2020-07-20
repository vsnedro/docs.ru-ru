---
title: Создание библиотеки классов .NET Standard с помощью Visual Studio Code
description: Сведения о создании библиотеки классов .NET Standard с помощью Visual Studio Code.
ms.date: 06/08/2020
ms.openlocfilehash: 714b5cf2125f1d296adc4a4dc7d1b6c9420417ed
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308888"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a><span data-ttu-id="8c7ea-103">Учебник. Создание библиотеки .NET Standard с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8c7ea-103">Tutorial: Create a .NET Standard library using Visual Studio Code</span></span>

<span data-ttu-id="8c7ea-104">В этом руководстве вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="8c7ea-105">Вы реализуете его как [метод расширения](../../csharp/programming-guide/classes-and-structs/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="8c7ea-106">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="8c7ea-107">Библиотеку классов, предназначенную для .NET Standard 2.0, можно вызывать из любой реализации .NET, которая поддерживает эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="8c7ea-108">Когда вы завершите создание библиотеки классов, можете распространить ее как независимый компонент или включить в состав одного или нескольких пакетов приложения.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c7ea-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8c7ea-109">Prerequisites</span></span>

1. <span data-ttu-id="8c7ea-110">Установленная платформа [Visual Studio Code](https://code.visualstudio.com/) с [расширением C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="8c7ea-110">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="8c7ea-111">См. сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="8c7ea-111">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="8c7ea-112">[Пакет SDK для .NET Core 3.1 или более поздней версии](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="8c7ea-112">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="8c7ea-113">Создание решения</span><span class="sxs-lookup"><span data-stu-id="8c7ea-113">Create a solution</span></span>

<span data-ttu-id="8c7ea-114">Начните с создания пустого решения для размещения проекта библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="8c7ea-115">Решение служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-115">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="8c7ea-116">Вы будете добавлять дополнительные связанные проекты в одно решение.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-116">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="8c7ea-117">Запустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-117">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="8c7ea-118">В главном меню выберите **Файл** > **Открыть папку** (в macOS щелкните **Открыть...** ).</span><span class="sxs-lookup"><span data-stu-id="8c7ea-118">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="8c7ea-119">В диалоговом окне **Открыть папку** создайте папку *ClassLibraryProjects* и щелкните **Выбор папки** (в macOS щелкните **Открыть**).</span><span class="sxs-lookup"><span data-stu-id="8c7ea-119">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="8c7ea-120">Откройте **терминал** в Visual Studio Code, выбрав в основном меню пункт **Вид** > **Терминал**.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="8c7ea-121">Откроется окно **Терминал** с командной строкой в папке *ClassLibraryProjects*.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="8c7ea-122">В **окне терминала** введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="8c7ea-123">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="8c7ea-124">Создание проекта библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="8c7ea-124">Create a class library project</span></span>

<span data-ttu-id="8c7ea-125">Добавьте в решение новый проект библиотеки классов .NET Standard с именем "StringLibrary".</span><span class="sxs-lookup"><span data-stu-id="8c7ea-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="8c7ea-126">В терминале выполните следующую команду, чтобы создать проект библиотеки классов:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="8c7ea-127">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="8c7ea-128">Чтобы добавить проект библиотеки в решение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="8c7ea-129">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="8c7ea-130">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="8c7ea-131">В **обозревателе** откройте файл *StringLibrary/StringLibrary.csproj*.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="8c7ea-132">Элемент `TargetFramework` показывает, что проект предназначен для .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="8c7ea-133">Откройте файл *Class1.cs* и замените его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="8c7ea-134">Библиотека классов `UtilityLibraries.StringLibrary` содержит метод `StartsWithUpper`,</span><span class="sxs-lookup"><span data-stu-id="8c7ea-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="8c7ea-135">который возвращает значение <xref:System.Boolean>, указывающее, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="8c7ea-136">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="8c7ea-137">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="8c7ea-138">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-138">Save the file.</span></span>

1. <span data-ttu-id="8c7ea-139">Выполните следующую команду, чтобы выполнить сборку решения и убедиться, что проект компилируется без ошибок.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="8c7ea-140">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-140">The terminal output looks like the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="8c7ea-141">Добавление консольного приложения в решение</span><span class="sxs-lookup"><span data-stu-id="8c7ea-141">Add a console app to the solution</span></span>

<span data-ttu-id="8c7ea-142">Добавьте консольное приложение, использующее библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="8c7ea-143">В приложении пользователю будет предложено ввести строку и сообщить, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="8c7ea-144">В терминале выполните следующую команду, чтобы создать проект консольного приложения:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="8c7ea-145">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="8c7ea-146">Чтобы добавить проект консольного приложения в решение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="8c7ea-147">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="8c7ea-148">Откройте файл *ShowCase/Program.cs* и замените все его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-148">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="8c7ea-149">В этом коде используется переменная `row` для сохранения количества строк данных, записываемых в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-149">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="8c7ea-150">Всякий раз, когда оно достигает значения 25 или превышает его, код очищает окно консоли и отображается сообщение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-150">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="8c7ea-151">Сама программа предлагает пользователю ввести строку.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-151">The program prompts the user to enter a string.</span></span> <span data-ttu-id="8c7ea-152">Она сообщает, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-152">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="8c7ea-153">Если пользователь нажимает клавишу <kbd>ВВОД</kbd>, не введя никакой строки, приложение завершает свою работу и окно консоли закрывается.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-153">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="8c7ea-154">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-154">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="8c7ea-155">Добавление ссылки на проект</span><span class="sxs-lookup"><span data-stu-id="8c7ea-155">Add a project reference</span></span>

<span data-ttu-id="8c7ea-156">Изначально новый проект консольного приложения не имеет доступа к библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-156">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="8c7ea-157">Чтобы позволить приложению вызывать методы из библиотеки классов, создайте в проекте ссылку на проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-157">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="8c7ea-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-158">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="8c7ea-159">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-159">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="8c7ea-160">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="8c7ea-160">Run the app</span></span>

1. <span data-ttu-id="8c7ea-161">Выполните следующую команду в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-161">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="8c7ea-162">Проверьте, как работает программа: вводите строки и нажимайте клавишу <kbd>ВВОД</kbd>. Чтобы выйти, нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-162">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="8c7ea-163">Выходные данные в терминале выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c7ea-163">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="8c7ea-164">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="8c7ea-164">Additional resources</span></span>

* [<span data-ttu-id="8c7ea-165">Разработка библиотек с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="8c7ea-165">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="8c7ea-166">[Список версий .NET Standard и поддерживаемых ими платформ](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="8c7ea-166">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8c7ea-167">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8c7ea-167">Next steps</span></span>

<span data-ttu-id="8c7ea-168">В этом руководстве вы создали решение, добавили проект библиотеки и добавили проект консольного приложения, использующего библиотеку.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-168">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="8c7ea-169">В следующем руководстве вы добавите в решение проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="8c7ea-169">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8c7ea-170">Тестирование библиотеки .NET Standard с помощью .NET Core и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8c7ea-170">Test a .NET Standard library with .NET Core using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
