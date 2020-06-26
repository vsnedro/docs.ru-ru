---
title: Создание консольного приложения .NET Core с помощью Visual Studio для Mac
description: Узнайте, как создать консольное приложение .NET Core с помощью Visual Studio для Mac.
ms.date: 06/02/2020
ms.openlocfilehash: 9cab838eaab2c59d8a0270267514f57acb7c60fb
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84811667"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="46698-103">Учебник. Создание консольного приложения .NET Core с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="46698-103">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="46698-104">В этом учебнике показано, как создать и запустить консольное приложение .NET Core с помощью Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="46698-104">This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="46698-105">Ваш отзыв очень важен.</span><span class="sxs-lookup"><span data-stu-id="46698-105">Your feedback is highly valued.</span></span> <span data-ttu-id="46698-106">Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами.</span><span class="sxs-lookup"><span data-stu-id="46698-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="46698-107">В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="46698-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="46698-108">Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="46698-108">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="46698-109">Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом открывается [веб-страница сообщества разработчиков Visual Studio для Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="46698-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46698-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="46698-110">Prerequisites</span></span>

* <span data-ttu-id="46698-111">[Visual Studio для Mac 8.6 или более поздней версии](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="46698-111">[Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="46698-112">Выберите вариант установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46698-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="46698-113">Установка Xamarin является необязательным шагом для разработки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46698-113">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="46698-114">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="46698-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="46698-115">[Учебник. Установка Visual Studio для Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="46698-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="46698-116">[Поддерживаемые версии macOS](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="46698-116">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="46698-117">[Версии .NET Core, поддерживаемые Visual Studio для Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="46698-117">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="46698-118">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="46698-118">Create the app</span></span>

<span data-ttu-id="46698-119">Создайте проект консольного приложения .NET Core с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="46698-119">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="46698-120">Запустите Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="46698-120">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="46698-121">Выберите **Создать** в окне запуска.</span><span class="sxs-lookup"><span data-stu-id="46698-121">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Кнопка Создать на экране запуска Visual Studio для Mac":::

1. <span data-ttu-id="46698-123">В узле **Web and Console** (Интернет и Консоль) диалогового окна **Создание проекта** выберите **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="46698-123">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="46698-124">Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="46698-124">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Список шаблонов для создания проектов":::

1. <span data-ttu-id="46698-126">В раскрывающемся списке **Целевая платформа** диалогового окна **Configure your new Console Application** (Настройка нового консольного приложения) выберите **.NET Core 3.1** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="46698-126">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1**, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Выбор целевой платформы":::

1. <span data-ttu-id="46698-128">Введите HelloWorld в поле **Имя проекта** и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="46698-128">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Диалоговое окно настройки нового консольного приложения":::

<span data-ttu-id="46698-130">Этот шаблон создает простое приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="46698-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="46698-131">Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения сообщения "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="46698-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="46698-132">в окне терминала.</span><span class="sxs-lookup"><span data-stu-id="46698-132">in the terminal window.</span></span>

<span data-ttu-id="46698-133">Код шаблона определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="46698-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="46698-134">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="46698-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="46698-135">Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив `args`.</span><span class="sxs-lookup"><span data-stu-id="46698-135">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="46698-136">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="46698-136">Run the app</span></span>

1. <span data-ttu-id="46698-137">Чтобы запустить приложение без отладки, выберите <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>Option</kbd>+<kbd>Command</kbd>+<kbd>ВВОД</kbd>).</span><span class="sxs-lookup"><span data-stu-id="46698-137">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="В терминале отобразится сообщение Hello World!":::

1. <span data-ttu-id="46698-139">Закройте окно **терминала**.</span><span class="sxs-lookup"><span data-stu-id="46698-139">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="46698-140">Улучшение приложения</span><span class="sxs-lookup"><span data-stu-id="46698-140">Enhance the app</span></span>

<span data-ttu-id="46698-141">Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.</span><span class="sxs-lookup"><span data-stu-id="46698-141">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="46698-142">В *Program.cs* замените содержимое метода `Main` (строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="46698-142">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="46698-143">Теперь код выдает строку "What is your name?" (Как вас зовут?)</span><span class="sxs-lookup"><span data-stu-id="46698-143">This code displays "What is your name?"</span></span> <span data-ttu-id="46698-144">в окне консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="46698-144">in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="46698-145">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="46698-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="46698-146">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`.</span><span class="sxs-lookup"><span data-stu-id="46698-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="46698-147">Наконец, оно отображает эти значения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="46698-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="46698-148">`\n` — это символ новой строки.</span><span class="sxs-lookup"><span data-stu-id="46698-148">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="46698-149">Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке.</span><span class="sxs-lookup"><span data-stu-id="46698-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="46698-150">Значение выражения вставляется в строку вместо выражения.</span><span class="sxs-lookup"><span data-stu-id="46698-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="46698-151">Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="46698-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="46698-152">Чтобы запустить приложение, выберите <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>Option</kbd>+<kbd>Command</kbd>+<kbd>ВВОД</kbd>).</span><span class="sxs-lookup"><span data-stu-id="46698-152">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="46698-153">В ответ на приглашение в командной строке введите имя и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="46698-153">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Терминал с измененными выходными данными программы":::

1. <span data-ttu-id="46698-155">Закройте терминал.</span><span class="sxs-lookup"><span data-stu-id="46698-155">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="46698-156">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="46698-156">Next steps</span></span>

<span data-ttu-id="46698-157">В этом руководстве показано, как создать консольное приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46698-157">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="46698-158">В следующем учебнике описывается отладка приложения.</span><span class="sxs-lookup"><span data-stu-id="46698-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="46698-159">Отладка консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46698-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio-mac.md)
