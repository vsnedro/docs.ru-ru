---
title: Создание консольного приложения .NET Core в Visual Studio Code
description: Узнайте, как создать консольное приложение .NET Core с помощью Visual Studio Code и .NET Core CLI.
ms.date: 05/22/2020
ms.openlocfilehash: 6d8f9adb2f77dbfd2d1cf54c80f1cdea582b1d96
ms.sourcegitcommit: f6350c2c542e6edd52d7e9d6667b96d85d810e67
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "84717514"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="1b59b-103">Учебник. Создание консольного приложения .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1b59b-103">Tutorial: Create a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="1b59b-104">В этом учебнике показано, как создать и запустить консольное приложение .NET Core с помощью Visual Studio Code и .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="1b59b-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="1b59b-105">Задачи проекта, такие как создание, компиляция и запуск проекта, выполняются с помощью .NET Core CLI,</span><span class="sxs-lookup"><span data-stu-id="1b59b-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET Core CLI.</span></span> <span data-ttu-id="1b59b-106">поэтому вы можете следовать этому руководству, используя при желании другой редактор кода и выполняя команды в терминале.</span><span class="sxs-lookup"><span data-stu-id="1b59b-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b59b-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1b59b-107">Prerequisites</span></span>

1. <span data-ttu-id="1b59b-108">Установленная платформа [Visual Studio Code](https://code.visualstudio.com/) с [расширением C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="1b59b-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="1b59b-109">См. сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="1b59b-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="1b59b-110">[Пакет SDK для .NET Core 3.1 или более поздней версии](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="1b59b-110">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="1b59b-111">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="1b59b-111">Create the app</span></span>

<span data-ttu-id="1b59b-112">Создайте проект консольного приложения .NET Core с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="1b59b-112">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="1b59b-113">Запустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1b59b-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="1b59b-114">В главном меню выберите **Файл** > **Открыть папку** (в macOS выберите **File** > **Open...**  (Файл > Открыть)).</span><span class="sxs-lookup"><span data-stu-id="1b59b-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="1b59b-115">В диалоговом окне **Открытие папки** создайте папку *HelloWorld* и щелкните **Выбрать папку** (в macOS щелкните **Open** (Открыть)).</span><span class="sxs-lookup"><span data-stu-id="1b59b-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="1b59b-116">Имя папки по умолчанию преобразуется в имя проекта и имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1b59b-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="1b59b-117">Вы добавите код позже в этом учебнике. Предполагается, что пространство имен проекта — `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="1b59b-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="1b59b-118">Откройте **терминал** в Visual Studio Code, выбрав в основном меню пункт **Вид** > **Терминал**.</span><span class="sxs-lookup"><span data-stu-id="1b59b-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="1b59b-119">Откроется окно **Терминал** с командной строкой в папке *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="1b59b-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="1b59b-120">В **окне терминала** введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1b59b-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="1b59b-121">Этот шаблон создает простое приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="1b59b-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="1b59b-122">Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения сообщения "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="1b59b-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="1b59b-123">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="1b59b-123">in the console window.</span></span>

<span data-ttu-id="1b59b-124">Код шаблона определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1b59b-124">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="1b59b-125">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="1b59b-125">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="1b59b-126">Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.</span><span class="sxs-lookup"><span data-stu-id="1b59b-126">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="1b59b-127">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="1b59b-127">Run the app</span></span>

<span data-ttu-id="1b59b-128">Выполните следующие команды в **окне терминала**:</span><span class="sxs-lookup"><span data-stu-id="1b59b-128">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="1b59b-129">В программе отобразится сообщение "Hello World!",</span><span class="sxs-lookup"><span data-stu-id="1b59b-129">The program displays "Hello World!"</span></span> <span data-ttu-id="1b59b-130">после чего она завершится.</span><span class="sxs-lookup"><span data-stu-id="1b59b-130">and ends.</span></span>

![Команда dotnet run](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="1b59b-132">Улучшение приложения</span><span class="sxs-lookup"><span data-stu-id="1b59b-132">Enhance the app</span></span>

<span data-ttu-id="1b59b-133">Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.</span><span class="sxs-lookup"><span data-stu-id="1b59b-133">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="1b59b-134">Откройте файл *Program.cs*, щелкнув его.</span><span class="sxs-lookup"><span data-stu-id="1b59b-134">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="1b59b-135">Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).</span><span class="sxs-lookup"><span data-stu-id="1b59b-135">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Откройте файл Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="1b59b-137">Когда в Visual Studio Code будет предложено добавить недостающие ресурсы для сборки и отладки приложения, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="1b59b-137">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="1b59b-139">В *Program.cs* замените содержимое метода `Main` (строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="1b59b-139">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="1":::

   <span data-ttu-id="1b59b-140">Теперь код выдает строку "What is your name?" (Как вас зовут?)</span><span class="sxs-lookup"><span data-stu-id="1b59b-140">This code displays "What is your name?"</span></span> <span data-ttu-id="1b59b-141">в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="1b59b-141">in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="1b59b-142">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="1b59b-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="1b59b-143">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`.</span><span class="sxs-lookup"><span data-stu-id="1b59b-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="1b59b-144">Наконец, оно отображает эти значения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="1b59b-144">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="1b59b-145">`\n` — это символ новой строки.</span><span class="sxs-lookup"><span data-stu-id="1b59b-145">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="1b59b-146">Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке.</span><span class="sxs-lookup"><span data-stu-id="1b59b-146">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="1b59b-147">Значение выражения вставляется в строку вместо выражения.</span><span class="sxs-lookup"><span data-stu-id="1b59b-147">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="1b59b-148">Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="1b59b-148">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="1b59b-149">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="1b59b-149">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1b59b-150">В Visual Studio Code необходимо явно сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="1b59b-150">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="1b59b-151">В отличие от Visual Studio, изменения файлов не сохраняются автоматически при сборке и запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="1b59b-151">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="1b59b-152">Запустите программу еще раз:</span><span class="sxs-lookup"><span data-stu-id="1b59b-152">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="1b59b-153">В ответ на приглашение в командной строке введите имя и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="1b59b-153">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Окно терминала с измененными выходными данными программы":::

1. <span data-ttu-id="1b59b-155">Нажмите любую клавишу для выхода из программы.</span><span class="sxs-lookup"><span data-stu-id="1b59b-155">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b59b-156">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="1b59b-156">Additional resources</span></span>

- <span data-ttu-id="1b59b-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="1b59b-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>

## <a name="next-steps"></a><span data-ttu-id="1b59b-158">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1b59b-158">Next steps</span></span>

<span data-ttu-id="1b59b-159">В этом руководстве показано, как создать консольное приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b59b-159">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="1b59b-160">В следующем учебнике описывается отладка приложения.</span><span class="sxs-lookup"><span data-stu-id="1b59b-160">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1b59b-161">Отладка консольного приложения .NET Core с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1b59b-161">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
