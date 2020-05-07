---
title: Начало работы с C# и Visual Studio Code
description: Узнайте, как создать и отладить в Visual Studio Code свое первое приложение .NET Core на языке C#.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506914"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="fb303-103">Начало работы с C# и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fb303-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="fb303-104">.NET Core предcтавляет собой быструю модульную платформу для создания приложений, работающих на ОС Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="fb303-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="fb303-105">Visual Studio Code с расширением C# позволяет эффективно работать с кодом, а также обеспечивает полную поддержку IntelliSense (интеллектуальное завершение кода) и отладки для языка C#.</span><span class="sxs-lookup"><span data-stu-id="fb303-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb303-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fb303-106">Prerequisites</span></span>

1. <span data-ttu-id="fb303-107">Установите [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="fb303-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="fb303-108">Установите [пакета SDK для .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="fb303-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="fb303-109">Установите [расширение C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fb303-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="fb303-110">См. дополнительные сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="fb303-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="fb303-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="fb303-111">Hello World</span></span>

<span data-ttu-id="fb303-112">Начните с создания простой программы Hello World для .NET Core:</span><span class="sxs-lookup"><span data-stu-id="fb303-112">Get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="fb303-113">Откройте проект.</span><span class="sxs-lookup"><span data-stu-id="fb303-113">Open a project:</span></span>

    - <span data-ttu-id="fb303-114">Откройте Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fb303-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="fb303-115">В главном меню выберите **Файл** > **Открыть папку**.</span><span class="sxs-lookup"><span data-stu-id="fb303-115">Select **File** > **Open Folder** from the main menu.</span></span>
    - <span data-ttu-id="fb303-116">Создайте папку с именем *HelloWorld* и щелкните **Выбрать папку**.</span><span class="sxs-lookup"><span data-stu-id="fb303-116">Create a folder named *HelloWorld*, and click **Select Folder**.</span></span> <span data-ttu-id="fb303-117">Имя папки по умолчанию преобразуется в имя проекта и имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fb303-117">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="fb303-118">Вы добавите код позже в этом учебнике. Предполагается, что пространство имен проекта — `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="fb303-118">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="fb303-119">Инициализируйте проект C#.</span><span class="sxs-lookup"><span data-stu-id="fb303-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="fb303-120">Откройте в Visual Studio Code терминал, выбрав **Просмотр** > **Терминал** в главном меню.</span><span class="sxs-lookup"><span data-stu-id="fb303-120">Open the Terminal from Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>
    - <span data-ttu-id="fb303-121">В окне терминала введите `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="fb303-121">In the terminal window, enter `dotnet new console`.</span></span>

      <span data-ttu-id="fb303-122">Эта команда создает в выбранной папке файл *Program.cs* с уже готовой простой программой Hello World, а также файл проекта C# с именем *HelloWorld.csproj*.</span><span class="sxs-lookup"><span data-stu-id="fb303-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![Команда dotnet new](media/with-visual-studio-code/dotnet-new-command.png)

1. <span data-ttu-id="fb303-124">Запустите программу Hello World.</span><span class="sxs-lookup"><span data-stu-id="fb303-124">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="fb303-125">В окне терминала введите `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="fb303-125">In the terminal window, enter `dotnet run`.</span></span>

      ![Команда dotnet run](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a><span data-ttu-id="fb303-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="fb303-127">Debug</span></span>

1. <span data-ttu-id="fb303-128">Откройте файл *Program.cs*, щелкнув его.</span><span class="sxs-lookup"><span data-stu-id="fb303-128">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="fb303-129">Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).</span><span class="sxs-lookup"><span data-stu-id="fb303-129">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Откройте файл Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="fb303-131">Visual Studio Code предлагает добавить недостающие ресурсы для сборки и отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="fb303-131">Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="fb303-132">Выберите ответ **Да**.</span><span class="sxs-lookup"><span data-stu-id="fb303-132">Select **Yes**.</span></span>

    ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="fb303-134">Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.</span><span class="sxs-lookup"><span data-stu-id="fb303-134">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Откройте вкладку "Отладка" в Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. <span data-ttu-id="fb303-136">Найдите зеленую стрелку в верхней части панели.</span><span class="sxs-lookup"><span data-stu-id="fb303-136">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="fb303-137">Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант **Запуск .NET Core (консоль)** .</span><span class="sxs-lookup"><span data-stu-id="fb303-137">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Выбор .NET Core в Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. <span data-ttu-id="fb303-139">Добавьте в проект точку останова, щелкнув **поле редактора** (пустое пространство слева от номеров строк) в строке 9, или переместите курсор текста в строку 9 в редакторе и нажмите клавишу <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fb303-139">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Установка точки останова](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. <span data-ttu-id="fb303-141">Чтобы начать отладку, нажмите клавишу <kbd>F5</kbd> или щелкните зеленую стрелку.</span><span class="sxs-lookup"><span data-stu-id="fb303-141">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="fb303-142">Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.</span><span class="sxs-lookup"><span data-stu-id="fb303-142">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="fb303-143">Во время отладки вы можете просматривать локальные переменные в верхней левой области или в консоли отладки.</span><span class="sxs-lookup"><span data-stu-id="fb303-143">While debugging, you can view your local variables in the top-left pane or use the debug console.</span></span>

1. <span data-ttu-id="fb303-144">Выберите синюю стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.</span><span class="sxs-lookup"><span data-stu-id="fb303-144">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Запуск и отладка в Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="fb303-146">Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="fb303-146">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="fb303-147">Добавление класса</span><span class="sxs-lookup"><span data-stu-id="fb303-147">Add a class</span></span>

1. <span data-ttu-id="fb303-148">Чтобы добавить новый класс, щелкните правой кнопкой мыши в обозревателе VS Code под *Program.cs* и выберите **Новый файл**.</span><span class="sxs-lookup"><span data-stu-id="fb303-148">To add a new class, right-click in the VSCode Explorer below *Program.cs* and select **New File**.</span></span> <span data-ttu-id="fb303-149">Так вы добавите новый файл в папку, открытую в VSCode.</span><span class="sxs-lookup"><span data-stu-id="fb303-149">This adds a new file to the folder you have open in VSCode.</span></span>
1. <span data-ttu-id="fb303-150">Назовите файл *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="fb303-150">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="fb303-151">Необходимо сохранить его с расширением `.cs`, чтобы он распознавался как файл С#.</span><span class="sxs-lookup"><span data-stu-id="fb303-151">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
1. <span data-ttu-id="fb303-152">Добавьте приведенный ниже код для создания класса.</span><span class="sxs-lookup"><span data-stu-id="fb303-152">Add the following code to create your first class.</span></span>

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

1. <span data-ttu-id="fb303-153">Вызовите новый класс из метода `Main`, заменив код в *Program.cs* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="fb303-153">Call your new class from your `Main` method by replacing the code in *Program.cs* with the following code:</span></span>

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

1. <span data-ttu-id="fb303-154">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="fb303-154">Save your changes.</span></span>

1. <span data-ttu-id="fb303-155">Запустите программу еще раз.</span><span class="sxs-lookup"><span data-stu-id="fb303-155">Run the program again.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="fb303-156">Должно отобразиться новое сообщение с добавленной строкой.</span><span class="sxs-lookup"><span data-stu-id="fb303-156">The new message appears with the appended string.</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="fb303-157">часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="fb303-157">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="fb303-158">Мне не хватает ресурсов для выполнения сборки и отладки C# в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fb303-158">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="fb303-159">Отладчик выдает сообщение: "Конфигурация отсутствует".</span><span class="sxs-lookup"><span data-stu-id="fb303-159">My debugger says "No Configuration."</span></span>

<span data-ttu-id="fb303-160">Ресурсы для сборки и отладки можно создать с помощью расширения Visual Studio Code C#.</span><span class="sxs-lookup"><span data-stu-id="fb303-160">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="fb303-161">Visual Studio Code предложит создать эти ресурсы при первом открытии проекта C#.</span><span class="sxs-lookup"><span data-stu-id="fb303-161">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="fb303-162">Если вы не создали ресурсы, вы все равно сможете выполнить эту команду. Для этого откройте палитру команд (**Вид > Палитра команд**) и введите ">.NET: Generate Assets for Build and Debug" (.NET: создать ресурсы для сборки и отладки).</span><span class="sxs-lookup"><span data-stu-id="fb303-162">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="fb303-163">После этого будут созданы необходимые файлы конфигурации *.vscode*, *launch.json* и *tasks.json*.</span><span class="sxs-lookup"><span data-stu-id="fb303-163">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb303-164">См. также</span><span class="sxs-lookup"><span data-stu-id="fb303-164">See also</span></span>

- <span data-ttu-id="fb303-165">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="fb303-165">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>
- <span data-ttu-id="fb303-166">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="fb303-166">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
