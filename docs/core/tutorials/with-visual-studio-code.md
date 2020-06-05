---
title: Создание консольного приложения с помощью .NET Core в Visual Studio Code
description: Узнайте, как создать консольное приложение .NET Core с помощью Visual Studio Code и .NET Core CLI.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201704"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a><span data-ttu-id="276e8-103">Учебник. Создание консольного приложения с помощью .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="276e8-103">Tutorial: Create a console application with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="276e8-104">В этом учебнике показано, как создать и запустить консольное приложение .NET Core с помощью Visual Studio Code и .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="276e8-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="276e8-105">Задачи проекта, такие как создание, компиляция и запуск проекта, выполняются с помощью интерфейса командной строки, поэтому вы можете следовать этому учебнику, используя другой редактор кода, и выполнять команды в терминале при желании.</span><span class="sxs-lookup"><span data-stu-id="276e8-105">Project tasks, such as creating, compiling, and running a project are done by using the CLI, so you can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="276e8-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="276e8-106">Prerequisites</span></span>

1. <span data-ttu-id="276e8-107">Установленная платформа [Visual Studio Code](https://code.visualstudio.com/) с [расширением C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="276e8-107">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="276e8-108">См. сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="276e8-108">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="276e8-109">[Пакет SDK для .NET Core 3.1 или более поздней версии](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="276e8-109">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="276e8-110">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="276e8-110">Create the app</span></span>

1. <span data-ttu-id="276e8-111">Откройте Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="276e8-111">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="276e8-112">Создайте проект.</span><span class="sxs-lookup"><span data-stu-id="276e8-112">Create a project.</span></span>

   1. <span data-ttu-id="276e8-113">В главном меню выберите **Файл** > **Открыть папку**/**Открыть**, создайте папку *HelloWorld* и нажмите **Выбрать папку**/**Открыть**.</span><span class="sxs-lookup"><span data-stu-id="276e8-113">Select **File** > **Open Folder**/**Open...** from the main menu, create a *HelloWorld* folder, and click **Select Folder**/**Open**.</span></span>

      <span data-ttu-id="276e8-114">Имя папки по умолчанию преобразуется в имя проекта и имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="276e8-114">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="276e8-115">Вы добавите код позже в этом учебнике. Предполагается, что пространство имен проекта — `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="276e8-115">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

   1. <span data-ttu-id="276e8-116">Откройте **терминал** в Visual Studio Code, выбрав в основном меню пункт **Вид** > **Терминал**.</span><span class="sxs-lookup"><span data-stu-id="276e8-116">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

      <span data-ttu-id="276e8-117">Откроется окно **Терминал** с командной строкой в папке *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="276e8-117">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

   1. <span data-ttu-id="276e8-118">В **окне терминала** введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="276e8-118">In the **Terminal**, enter the following command:</span></span>

      ```dotnetcli
      dotnet new console
      ```

<span data-ttu-id="276e8-119">Шаблон консольного приложения для .NET Core определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="276e8-119">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="276e8-120">В файле *Program.cs* находится следующий код:</span><span class="sxs-lookup"><span data-stu-id="276e8-120">The *Program.cs* file has the following code:</span></span>

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

<span data-ttu-id="276e8-121">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="276e8-121">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="276e8-122">Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.</span><span class="sxs-lookup"><span data-stu-id="276e8-122">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="276e8-123">Шаблон создает простое приложение, которое вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для вывода сообщения "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="276e8-123">The template creates a simple application that calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="276e8-124">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="276e8-124">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="276e8-125">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="276e8-125">Run the app</span></span>

<span data-ttu-id="276e8-126">Выполните следующие команды в **окне терминала**:</span><span class="sxs-lookup"><span data-stu-id="276e8-126">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="276e8-127">В программе отобразится сообщение "Hello World!",</span><span class="sxs-lookup"><span data-stu-id="276e8-127">The program displays "Hello World!"</span></span> <span data-ttu-id="276e8-128">после чего она завершится.</span><span class="sxs-lookup"><span data-stu-id="276e8-128">and ends.</span></span>

![Команда dotnet run](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="276e8-130">Улучшение приложения</span><span class="sxs-lookup"><span data-stu-id="276e8-130">Enhance the app</span></span>

<span data-ttu-id="276e8-131">Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.</span><span class="sxs-lookup"><span data-stu-id="276e8-131">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="276e8-132">Откройте файл *Program.cs*, щелкнув его.</span><span class="sxs-lookup"><span data-stu-id="276e8-132">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="276e8-133">Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).</span><span class="sxs-lookup"><span data-stu-id="276e8-133">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Откройте файл Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="276e8-135">Когда в Visual Studio Code будет предложено добавить недостающие ресурсы для сборки и отладки приложения, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="276e8-135">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="276e8-137">Замените содержимое метода `Main` в файле *Program.cs* (в настоящий момент это просто строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="276e8-137">Replace the contents of the `Main` method in *Program.cs*, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   <span data-ttu-id="276e8-138">Теперь код выдает строку "What is your name?" (Как вас зовут?)</span><span class="sxs-lookup"><span data-stu-id="276e8-138">This code displays "What is your name?"</span></span> <span data-ttu-id="276e8-139">в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="276e8-139">in the console window and waits until the user enters a string followed by the **Enter** key.</span></span> <span data-ttu-id="276e8-140">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="276e8-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="276e8-141">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`.</span><span class="sxs-lookup"><span data-stu-id="276e8-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="276e8-142">Наконец, оно отображает эти значения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="276e8-142">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="276e8-143">`\n` — это символ новой строки.</span><span class="sxs-lookup"><span data-stu-id="276e8-143">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="276e8-144">Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке.</span><span class="sxs-lookup"><span data-stu-id="276e8-144">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="276e8-145">Значение выражения вставляется в строку вместо выражения.</span><span class="sxs-lookup"><span data-stu-id="276e8-145">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="276e8-146">Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="276e8-146">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="276e8-147">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="276e8-147">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="276e8-148">В Visual Studio Code необходимо явно сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="276e8-148">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="276e8-149">В отличие от Visual Studio, изменения файлов не сохраняются автоматически при сборке и запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="276e8-149">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="276e8-150">Запустите программу еще раз:</span><span class="sxs-lookup"><span data-stu-id="276e8-150">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="276e8-151">В ответ на приглашение в командной строке введите имя и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="276e8-151">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Окно терминала с измененными выходными данными программы":::

1. <span data-ttu-id="276e8-153">Нажмите любую клавишу для выхода из программы.</span><span class="sxs-lookup"><span data-stu-id="276e8-153">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="276e8-154">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="276e8-154">Additional resources</span></span>

- <span data-ttu-id="276e8-155">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="276e8-155">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>

## <a name="next-steps"></a><span data-ttu-id="276e8-156">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="276e8-156">Next steps</span></span>

<span data-ttu-id="276e8-157">В этом учебнике вы создали приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="276e8-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="276e8-158">В следующем учебнике описывается отладка приложения.</span><span class="sxs-lookup"><span data-stu-id="276e8-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="276e8-159">Отладка консольного приложения .NET Core с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="276e8-159">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
