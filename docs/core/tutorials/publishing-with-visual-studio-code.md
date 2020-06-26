---
title: Публикация консольного приложения .NET Core с помощью Visual Studio Code
description: При публикации создается набор файлов, которые необходимы для запуска приложения .NET Core.
ms.date: 06/08/2020
ms.openlocfilehash: 442d08c9b016407327ba30db0aae78b5cf6b6fe3
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701454"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="78d30-103">Учебник. Публикация консольного приложения .NET Core с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="78d30-103">Tutorial: Publish a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="78d30-104">В этом руководстве показано, как опубликовать консольное приложение, чтобы его могли запускать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="78d30-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="78d30-105">При публикации создается набор файлов, которые необходимы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-105">Publishing creates the set of files that are needed to run an application.</span></span> <span data-ttu-id="78d30-106">Чтобы развернуть файлы, скопируйте их на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="78d30-106">To deploy the files, copy them to the target machine.</span></span>

<span data-ttu-id="78d30-107">Для публикации приложения используется .NET Core CLI, поэтому приведенные в этом руководстве действия при желании можно выполнять в редакторе кода, отличном от Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="78d30-107">The .NET Core CLI is used to publish the app, so you can follow this tutorial with a code editor other than Visual Studio Code if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78d30-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="78d30-108">Prerequisites</span></span>

- <span data-ttu-id="78d30-109">В этом руководстве используется консольное приложение, созданное в руководстве [Создание консольного приложения .NET Core в Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="78d30-109">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="78d30-110">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="78d30-110">Publish the app</span></span>

1. <span data-ttu-id="78d30-111">Запустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="78d30-111">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="78d30-112">Откройте папку проекта *HelloWorld*, созданного в руководстве [Создание консольного приложения .NET Core в Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="78d30-112">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="78d30-113">В главном меню выберите **Вид** > **Терминал**.</span><span class="sxs-lookup"><span data-stu-id="78d30-113">Choose **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="78d30-114">Терминал откроется в папке *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="78d30-114">The terminal opens in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="78d30-115">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78d30-115">Run the following command:</span></span>

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   <span data-ttu-id="78d30-116">По умолчанию используется конфигурация сборки *Отладка*, поэтому эта команда задает конфигурацию сборки *Выпуск*.</span><span class="sxs-lookup"><span data-stu-id="78d30-116">The default build configuration is *Debug*, so this command specifies the *Release* build configuration.</span></span> <span data-ttu-id="78d30-117">Выходные данные конфигурации сборки "Выпуск" содержат минимальную символическую отладочную информацию и полностью оптимизированы.</span><span class="sxs-lookup"><span data-stu-id="78d30-117">The output from the Release build configuration has minimal symbolic debug information and is fully optimized.</span></span>

   <span data-ttu-id="78d30-118">Результат команды должен быть примерно таким:</span><span class="sxs-lookup"><span data-stu-id="78d30-118">The command output is similar to the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a><span data-ttu-id="78d30-119">Проверка файлов</span><span class="sxs-lookup"><span data-stu-id="78d30-119">Inspect the files</span></span>

<span data-ttu-id="78d30-120">По умолчанию в ходе публикации создается платформенно-зависимое развертывание. При таком развертывании опубликованное приложение выполняется на компьютере с установленной средой выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="78d30-120">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="78d30-121">Чтобы запустить опубликованное приложение, можно использовать исполняемый файл или выполнить команду `dotnet HelloWorld.dll` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="78d30-121">To run the published app you can use the executable file or run the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="78d30-122">В следующих шагах будут рассмотрены файлы, созданные в процессе публикации.</span><span class="sxs-lookup"><span data-stu-id="78d30-122">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="78d30-123">Выберите **Обозреватель** на панели навигации слева.</span><span class="sxs-lookup"><span data-stu-id="78d30-123">Select the **Explorer** in the left navigation bar.</span></span>

1. <span data-ttu-id="78d30-124">Разверните узел *bin/Release/netcoreapp3.1/publish*.</span><span class="sxs-lookup"><span data-stu-id="78d30-124">Expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Опубликованные файлы в обозревателе":::

   <span data-ttu-id="78d30-126">Как показано на рисунке, опубликованные выходные данные включают следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="78d30-126">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="78d30-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="78d30-127">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="78d30-128">Это файл зависимостей среды выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="78d30-129">Он определяет библиотеки и компоненты .NET Core (включая библиотеку DLL, содержащую приложение), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-129">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="78d30-130">Дополнительные сведения см. в разделе [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (Файлы конфигурации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="78d30-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="78d30-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="78d30-131">*HelloWorld.dll*</span></span>

      <span data-ttu-id="78d30-132">Это версия [зависимого от платформы развертывания](../deploying/deploy-with-cli.md#framework-dependent-deployment) приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="78d30-133">Чтобы выполнить эту библиотеку динамической компоновки, введите `dotnet HelloWorld.dll` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="78d30-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="78d30-134">Этот метод запуска приложения работает на любой платформе, где установлена среда выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="78d30-134">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="78d30-135">*HelloWorld.exe* (приложение *HelloWorld* в Linux, не созданное в macOS.)</span><span class="sxs-lookup"><span data-stu-id="78d30-135">*HelloWorld.exe* (*HelloWorld* on Linux, not created on macOS.)</span></span>

      <span data-ttu-id="78d30-136">Это версия [исполняемого, зависящего от платформы файла](../deploying/deploy-with-cli.md#framework-dependent-executable) приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-136">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="78d30-137">Файл зависит от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="78d30-137">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="78d30-138">*HelloWorld.pdb* (необязателен для развертывания)</span><span class="sxs-lookup"><span data-stu-id="78d30-138">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="78d30-139">Это файл отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="78d30-139">This is the debug symbols file.</span></span> <span data-ttu-id="78d30-140">Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-140">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="78d30-141">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="78d30-141">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="78d30-142">Это файл конфигурации среды выполнения для приложения.</span><span class="sxs-lookup"><span data-stu-id="78d30-142">This is the application's run-time configuration file.</span></span> <span data-ttu-id="78d30-143">Он определяет версию платформы .NET Core, для которой предназначено приложение.</span><span class="sxs-lookup"><span data-stu-id="78d30-143">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="78d30-144">Кроме того, в него можно добавить параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="78d30-144">You can also add configuration options to it.</span></span> <span data-ttu-id="78d30-145">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="78d30-145">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="78d30-146">Запуск опубликованного приложения</span><span class="sxs-lookup"><span data-stu-id="78d30-146">Run the published app</span></span>

1. <span data-ttu-id="78d30-147">В **обозревателе** щелкните правой кнопкой мыши папку *publish* (в macOS нажмите <kbd>CTRL</kbd>+щелчок) и выберите **Открыть в терминале**.</span><span class="sxs-lookup"><span data-stu-id="78d30-147">In **Explorer**, right-click the *publish* folder (<kbd>Ctrl</kbd>-click on macOS), and select **Open in Terminal**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Контекстное меню с командой Открыть в терминале":::

1. <span data-ttu-id="78d30-149">В Windows или Linux запустите приложение с помощью исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="78d30-149">On Windows or Linux, run the app by using the executable.</span></span>

   1. <span data-ttu-id="78d30-150">В Windows введите `.\HelloWorld.exe` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="78d30-150">On Windows, enter `.\HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="78d30-151">В Linux введите `./HelloWorld` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="78d30-151">On Linux, enter `./HelloWorld` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="78d30-152">В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="78d30-152">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="78d30-153">На любой платформе запустите приложение с помощью команды [`dotnet`](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="78d30-153">On any platform, run the app by using the  [`dotnet`](../tools/dotnet.md) command:</span></span>

   1. <span data-ttu-id="78d30-154">Введите `dotnet HelloWorld.dll` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="78d30-154">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="78d30-155">В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="78d30-155">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78d30-156">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="78d30-156">Additional resources</span></span>

- [<span data-ttu-id="78d30-157">Развертывание приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="78d30-157">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="78d30-158">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="78d30-158">Next steps</span></span>

<span data-ttu-id="78d30-159">В этом руководстве вы опубликовали консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="78d30-159">In this tutorial, you published a console app.</span></span> <span data-ttu-id="78d30-160">Далее вы создадите библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="78d30-160">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78d30-161">Создание библиотеки .NET Standard в Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="78d30-161">Create a .NET Standard library in Visual Studio for Mac</span></span>](library-with-visual-studio-mac.md)
