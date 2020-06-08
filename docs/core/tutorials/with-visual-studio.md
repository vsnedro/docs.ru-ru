---
title: Создание консольного приложения с помощью .NET Core в Visual Studio
description: Узнайте, как консольное приложение .NET Core с помощью C# или Visual Basic в Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 144d7bb087034839ad2cde2fa28a4961cff4321f
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306998"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="bd941-103">Учебник. Создание консольного приложения .NET Core в Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bd941-103">Tutorial: Create a .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="bd941-104">В этом учебнике показано, как создать и запустить консольное приложение .NET Core в помощью Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="bd941-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd941-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bd941-105">Prerequisites</span></span>

- <span data-ttu-id="bd941-106">[Visual Studio 2019 версии 16.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="bd941-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="bd941-107">Пакет SDK для .NET Core 3.1 устанавливается автоматически при выборе этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="bd941-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="bd941-108">Дополнительные сведения см. в разделе [Установка с помощью Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) статьи [Установка пакета SDK для .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="bd941-108">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="bd941-109">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="bd941-109">Create the app</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="bd941-110">Запустите Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="bd941-110">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="bd941-111">Создайте проект консольного приложения .NET Core с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="bd941-111">Create a new .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="bd941-112">На начальной странице выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="bd941-112">On the start page, choose **Create a new project**.</span></span>

      ![Кнопка "Создать проект", выбранная на начальной странице Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="bd941-114">На странице **Создание проекта** введите в поле поиска **консоль**.</span><span class="sxs-lookup"><span data-stu-id="bd941-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="bd941-115">Затем выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="bd941-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="bd941-116">Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd941-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Окно "Создание проекта" с выбранными фильтрами](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="bd941-118">Если вы не видите шаблоны .NET Core, вероятно, у вас не установлена требуемая рабочая нагрузка.</span><span class="sxs-lookup"><span data-stu-id="bd941-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="bd941-119">В сообщении **Не удается найти то, что ищете?** выберите ссылку **Установка других средств и компонентов**.</span><span class="sxs-lookup"><span data-stu-id="bd941-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="bd941-120">Откроется Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="bd941-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="bd941-121">Убедитесь, что у вас установлена рабочая нагрузка **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="bd941-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="bd941-122">На странице **настройки нового проекта** введите **HelloWorld** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="bd941-122">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="bd941-123">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bd941-123">Then choose **Create**.</span></span>

      ![Окно настройки нового проекта с полями имени проекта, расположения и имени решения](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="bd941-125">Шаблон консольного приложения для .NET Core определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="bd941-125">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="bd941-126">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="bd941-126">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="bd941-127">Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.</span><span class="sxs-lookup"><span data-stu-id="bd941-127">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   <span data-ttu-id="bd941-128">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="bd941-128">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   <span data-ttu-id="bd941-129">Этот шаблон создает простое приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="bd941-129">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="bd941-130">Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения сообщения "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="bd941-130">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="bd941-131">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="bd941-131">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="bd941-132">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="bd941-132">Run the app</span></span>

1. <span data-ttu-id="bd941-133">Чтобы запустить программу, выберите **HelloWorld** на панели инструментов или нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="bd941-133">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Панель инструментов Visual Studio с выбранной кнопкой запуска HelloWorld](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="bd941-135">Откроется окно консоли с текстом "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="bd941-135">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="bd941-136">на экране и информацией об отладке Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bd941-136">printed on the screen and some Visual Studio debug information.</span></span>

   ![Окно консоли с приложением Hello World и надписью "Чтобы продолжить, нажмите любую клавишу"](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="bd941-138">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="bd941-138">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="bd941-139">Улучшение приложения</span><span class="sxs-lookup"><span data-stu-id="bd941-139">Enhance the app</span></span>

<span data-ttu-id="bd941-140">Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.</span><span class="sxs-lookup"><span data-stu-id="bd941-140">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="bd941-141">Ниже приведены инструкции по изменению приложения и его повторному запуску:</span><span class="sxs-lookup"><span data-stu-id="bd941-141">The following instructions modify the app and run it again:</span></span>

1. <span data-ttu-id="bd941-142">Замените содержимое метода `Main` (в настоящий момент это просто строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="bd941-142">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](./snippets/with-visual-studio/csharp/Program.cs#1)]
   [!code-vb[GettingStarted#1](./snippets/with-visual-studio/vb/Program.vb#1)]

   <span data-ttu-id="bd941-143">Теперь код выдает строку "What is your name?" (Как вас зовут?)</span><span class="sxs-lookup"><span data-stu-id="bd941-143">This code displays "What is your name?"</span></span> <span data-ttu-id="bd941-144">в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bd941-144">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="bd941-145">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="bd941-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="bd941-146">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date` (`currentDate` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="bd941-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="bd941-147">Наконец, оно отображает эти значения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="bd941-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="bd941-148">`\n` (`vbCrLf` в Visual Basic) представляет собой символ новой строки.</span><span class="sxs-lookup"><span data-stu-id="bd941-148">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="bd941-149">Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке.</span><span class="sxs-lookup"><span data-stu-id="bd941-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="bd941-150">Значение выражения вставляется в строку вместо выражения.</span><span class="sxs-lookup"><span data-stu-id="bd941-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="bd941-151">Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="bd941-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="bd941-152">Чтобы запустить программу, выберите **HelloWorld** на панели инструментов или нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="bd941-152">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="bd941-153">В ответ на приглашение в командной строке введите имя и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="bd941-153">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="bd941-155">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="bd941-155">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd941-156">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="bd941-156">Next steps</span></span>

<span data-ttu-id="bd941-157">В этом учебнике вы создали приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd941-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="bd941-158">В следующем учебнике описывается отладка приложения.</span><span class="sxs-lookup"><span data-stu-id="bd941-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bd941-159">Отладка консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bd941-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
