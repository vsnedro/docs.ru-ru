---
title: Публикация приложения Hello World .NET Core в Visual Studio
description: При публикации создается набор файлов, которые необходимы для запуска приложения .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 745fb2af332afa278c78ec9baeea7230fe725c02
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241502"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="ae3f0-103">Учебник. Публикация консольного приложения .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae3f0-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="ae3f0-104">В этом руководстве показано, как опубликовать консольное приложение, чтобы его могли запускать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="ae3f0-105">При публикации создается набор файлов, которые необходимы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="ae3f0-106">Чтобы развернуть файлы, скопируйте их на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae3f0-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ae3f0-107">Prerequisites</span></span>

- <span data-ttu-id="ae3f0-108">В этом руководстве используется консольное приложение, созданное в руководстве [Создание консольного приложения .NET Core в Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ae3f0-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="ae3f0-109">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="ae3f0-109">Publish the app</span></span>

1. <span data-ttu-id="ae3f0-110">Убедитесь, что в Visual Studio настроен режим сборки для версии выпуска.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="ae3f0-111">При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Панель инструментов Visual Studio с выбранной сборкой выпуска](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="ae3f0-113">Щелкните проект **HelloWorld** (не решение HelloWorld) правой кнопкой мыши и выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Контекстное меню "Опубликовать" в Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="ae3f0-115">На вкладке **Целевой объект** на странице **Публикация** выберите **Папка**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Выбор целевого объекта публикации в Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="ae3f0-117">На вкладке **Расположение** на странице **Публикация** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Вкладка "Расположение" на странице "Публикация" в Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="ae3f0-119">На вкладке **Публикация** в окне **Публикация** нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Окно публикации в Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="ae3f0-121">Проверка файлов</span><span class="sxs-lookup"><span data-stu-id="ae3f0-121">Inspect the files</span></span>

<span data-ttu-id="ae3f0-122">В ходе публикации создается платформенно-зависимое развертывание. При таком развертывании опубликованное приложение выполняется на компьютере с установленной средой выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="ae3f0-123">Пользователи могут запустить опубликованное приложение, дважды щелкнув исполняемый файл или выполнив команду `dotnet HelloWorld.dll` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="ae3f0-124">В следующих шагах будут рассмотрены файлы, созданные в процессе публикации.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="ae3f0-125">В **обозревателе решений** выберите **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="ae3f0-126">В папке проекта разверните узел *bin/Release/netcoreapp3.1/publish*.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Опубликованные файлы в обозревателе решений":::

   <span data-ttu-id="ae3f0-128">Как показано на рисунке, опубликованные выходные данные включают следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="ae3f0-128">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="ae3f0-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="ae3f0-129">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="ae3f0-130">Это файл зависимостей среды выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="ae3f0-131">Он определяет библиотеки и компоненты .NET Core (включая библиотеку DLL, содержащую приложение), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="ae3f0-132">Дополнительные сведения см. в разделе [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (Файлы конфигурации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="ae3f0-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="ae3f0-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="ae3f0-133">*HelloWorld.dll*</span></span>

      <span data-ttu-id="ae3f0-134">Это версия [зависимого от платформы развертывания](../deploying/deploy-with-cli.md#framework-dependent-deployment) приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="ae3f0-135">Чтобы выполнить эту библиотеку динамической компоновки, введите `dotnet HelloWorld.dll` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="ae3f0-136">Этот метод запуска приложения работает на любой платформе, где установлена среда выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-136">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="ae3f0-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="ae3f0-137">*HelloWorld.exe*</span></span>

      <span data-ttu-id="ae3f0-138">Это версия [исполняемого, зависящего от платформы файла](../deploying/deploy-with-cli.md#framework-dependent-executable) приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="ae3f0-139">Чтобы запустить его, введите `HelloWorld.exe` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="ae3f0-140">Файл зависит от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-140">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="ae3f0-141">*HelloWorld.pdb* (необязателен для развертывания)</span><span class="sxs-lookup"><span data-stu-id="ae3f0-141">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="ae3f0-142">Это файл отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-142">This is the debug symbols file.</span></span> <span data-ttu-id="ae3f0-143">Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-143">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="ae3f0-144">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="ae3f0-144">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="ae3f0-145">Это файл конфигурации среды выполнения для приложения.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-145">This is the application's run-time configuration file.</span></span> <span data-ttu-id="ae3f0-146">Он определяет версию платформы .NET Core, для которой предназначено приложение.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-146">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="ae3f0-147">Кроме того, в него можно добавить параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-147">You can also add configuration options to it.</span></span> <span data-ttu-id="ae3f0-148">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="ae3f0-148">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="ae3f0-149">Запуск опубликованного приложения</span><span class="sxs-lookup"><span data-stu-id="ae3f0-149">Run the published app</span></span>

1. <span data-ttu-id="ae3f0-150">В **обозревателе решений** щелкните папку *publish* правой кнопкой мыши и выберите команду **Копировать полный путь**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-150">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="ae3f0-151">Откройте командную строку и перейдите к папке *publish*.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-151">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="ae3f0-152">Введите `cd` и вставьте полный путь.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-152">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="ae3f0-153">Пример:</span><span class="sxs-lookup"><span data-stu-id="ae3f0-153">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="ae3f0-154">Запустите приложение с помощью исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="ae3f0-154">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="ae3f0-155">Введите `HelloWorld.exe` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-155">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="ae3f0-156">В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-156">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="ae3f0-157">Запустите приложение с помощью команды `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="ae3f0-157">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="ae3f0-158">Введите `dotnet HelloWorld.dll` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-158">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="ae3f0-159">В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-159">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ae3f0-160">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ae3f0-160">Additional resources</span></span>

- [<span data-ttu-id="ae3f0-161">Развертывание приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="ae3f0-161">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="ae3f0-162">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ae3f0-162">Next steps</span></span>

<span data-ttu-id="ae3f0-163">В этом руководстве вы опубликовали консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-163">In this tutorial, you published a console app.</span></span> <span data-ttu-id="ae3f0-164">Далее вы создадите библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-164">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ae3f0-165">Создание библиотеки .NET Standard в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae3f0-165">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
