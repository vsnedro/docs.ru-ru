---
title: Создание консольного приложения .NET Core в Visual Studio
description: Узнайте, как консольное приложение .NET Core с помощью C# или Visual Basic в Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4cd18aca4396f902268d59867760424d65ddcf6d
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867637"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="553a6-103">Учебник. Создание консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="553a6-103">Tutorial: Create a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="553a6-104">В этом учебнике показано, как создать и запустить консольное приложение .NET Core в помощью Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="553a6-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="553a6-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="553a6-105">Prerequisites</span></span>

- <span data-ttu-id="553a6-106">[Visual Studio 2019 версии 16.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="553a6-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="553a6-107">Пакет SDK для .NET Core 3.1 устанавливается автоматически при выборе этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="553a6-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="553a6-108">См. раздел [Установка с помощью Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="553a6-108">For more information, see [Install the .NET Core SDK with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="553a6-109">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="553a6-109">Create the app</span></span>

<span data-ttu-id="553a6-110">Создайте проект консольного приложения .NET Core с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="553a6-110">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="553a6-111">Запустите Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="553a6-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="553a6-112">На начальной странице выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="553a6-112">On the start page, choose **Create a new project**.</span></span>

   ![Кнопка "Создать проект", выбранная на начальной странице Visual Studio](./media/with-visual-studio/start-window.png)

1. <span data-ttu-id="553a6-114">На странице **Создание проекта** введите в поле поиска **консоль**.</span><span class="sxs-lookup"><span data-stu-id="553a6-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="553a6-115">Затем выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="553a6-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="553a6-116">Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="553a6-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   ![Окно "Создание проекта" с выбранными фильтрами](./media/with-visual-studio/create-new-project.png)

   > [!TIP]
   > <span data-ttu-id="553a6-118">Если вы не видите шаблоны .NET Core, вероятно, у вас не установлена требуемая рабочая нагрузка.</span><span class="sxs-lookup"><span data-stu-id="553a6-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="553a6-119">В сообщении **Не удается найти то, что ищете?** выберите ссылку **Установка других средств и компонентов**.</span><span class="sxs-lookup"><span data-stu-id="553a6-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="553a6-120">Откроется Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="553a6-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="553a6-121">Убедитесь, что у вас установлена рабочая нагрузка **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="553a6-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="553a6-122">В диалоговом окне **Настройка нового проекта** в поле **Имя проекта** введите **HelloWorld**.</span><span class="sxs-lookup"><span data-stu-id="553a6-122">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="553a6-123">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="553a6-123">Then choose **Create**.</span></span>

   ![Окно настройки нового проекта с полями имени проекта, расположения и имени решения](./media/with-visual-studio/configure-new-project.png)

<span data-ttu-id="553a6-125">Этот шаблон создает простое приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="553a6-125">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="553a6-126">Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения сообщения "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="553a6-126">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="553a6-127">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="553a6-127">in the console window.</span></span>

<span data-ttu-id="553a6-128">Код шаблона определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="553a6-128">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="553a6-129">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="553a6-129">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="553a6-130">Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.</span><span class="sxs-lookup"><span data-stu-id="553a6-130">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="553a6-131">Если нужный язык не отображается, измените выбор языка в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="553a6-131">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="553a6-132">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="553a6-132">Run the app</span></span>

1. <span data-ttu-id="553a6-133">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>F5</kbd>, чтобы запустить программу без отладки.</span><span class="sxs-lookup"><span data-stu-id="553a6-133">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="553a6-134">Откроется окно консоли с текстом "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="553a6-134">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="553a6-135">на экране и информацией об отладке Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="553a6-135">printed on the screen and some Visual Studio debug information.</span></span>

   ![Окно консоли с приложением Hello World и надписью "Чтобы продолжить, нажмите любую клавишу"](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="553a6-137">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="553a6-137">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="553a6-138">Улучшение приложения</span><span class="sxs-lookup"><span data-stu-id="553a6-138">Enhance the app</span></span>

<span data-ttu-id="553a6-139">Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.</span><span class="sxs-lookup"><span data-stu-id="553a6-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="553a6-140">В *Program.cs* или *Program.vb* замените содержимое метода `Main` (строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="553a6-140">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="553a6-141">Этот код отображает запрос в окне консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="553a6-141">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="553a6-142">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="553a6-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="553a6-143">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date` (`currentDate` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="553a6-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="553a6-144">Затем оно отображает эти значения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="553a6-144">And it displays these values in the console window.</span></span> <span data-ttu-id="553a6-145">Наконец, приложение выводит запрос в окне консоли и вызывает метод <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> для ожидания ввода данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="553a6-145">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="553a6-146">`\n` (`vbCrLf` в Visual Basic) представляет собой символ новой строки.</span><span class="sxs-lookup"><span data-stu-id="553a6-146">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="553a6-147">Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке.</span><span class="sxs-lookup"><span data-stu-id="553a6-147">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="553a6-148">Значение выражения вставляется в строку вместо выражения.</span><span class="sxs-lookup"><span data-stu-id="553a6-148">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="553a6-149">Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="553a6-149">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="553a6-150">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>F5</kbd>, чтобы запустить программу без отладки.</span><span class="sxs-lookup"><span data-stu-id="553a6-150">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="553a6-151">В ответ на приглашение в командной строке введите имя и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="553a6-151">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="553a6-153">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="553a6-153">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="553a6-154">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="553a6-154">Next steps</span></span>

<span data-ttu-id="553a6-155">В этом руководстве показано, как создать консольное приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="553a6-155">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="553a6-156">В следующем учебнике описывается отладка приложения.</span><span class="sxs-lookup"><span data-stu-id="553a6-156">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="553a6-157">Отладка консольного приложения .NET Core с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="553a6-157">Debug a .NET Core console application using Visual Studio</span></span>](debugging-with-visual-studio.md)
