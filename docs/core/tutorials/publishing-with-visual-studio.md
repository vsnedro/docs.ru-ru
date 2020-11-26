---
title: Публикация консольного приложения .NET с помощью Visual Studio
description: Узнайте, как использовать Visual Studio для создания набора файлов, необходимых для запуска приложения .NET.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916033"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a><span data-ttu-id="201f1-103">Учебник. Публикация консольного приложения .NET с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="201f1-103">Tutorial: Publish a .NET console application using Visual Studio</span></span>

<span data-ttu-id="201f1-104">В этом руководстве показано, как опубликовать консольное приложение, чтобы его могли запускать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="201f1-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="201f1-105">При публикации создается набор файлов, которые необходимы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="201f1-106">Чтобы развернуть файлы, скопируйте их на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="201f1-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="201f1-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="201f1-107">Prerequisites</span></span>

- <span data-ttu-id="201f1-108">В этом руководстве используется консольное приложение, созданное в руководстве [Создание консольного приложения .NET в Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="201f1-108">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="201f1-109">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="201f1-109">Publish the app</span></span>

1. <span data-ttu-id="201f1-110">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="201f1-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="201f1-111">Откройте проект *HelloWorld*, созданный по инструкциям из статьи [Создание консольного приложения .NET в Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="201f1-111">Open the *HelloWorld* project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="201f1-112">Убедитесь, что в Visual Studio используется конфигурация сборки Release.</span><span class="sxs-lookup"><span data-stu-id="201f1-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="201f1-113">При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="201f1-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Панель инструментов Visual Studio с выбранной сборкой выпуска":::

1. <span data-ttu-id="201f1-115">Щелкните проект **HelloWorld** (не решение HelloWorld) правой кнопкой мыши и выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="201f1-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Контекстное меню Опубликовать в Visual Studio":::

1. <span data-ttu-id="201f1-117">На вкладке **Целевой объект** на странице **Публикация** выберите **Папка**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="201f1-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Выбор целевого объекта публикации в Visual Studio":::

1. <span data-ttu-id="201f1-119">На вкладке **Определенный целевой объект** на странице **Публикация** выберите **Папка**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="201f1-119">On the **Specific Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Выбор определенного целевого объекта публикации в Visual Studio":::

1. <span data-ttu-id="201f1-121">На вкладке **Расположение** на странице **Публикация** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="201f1-121">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Вкладка &quot;Расположение&quot; на странице &quot;Публикация&quot; в Visual Studio":::

1. <span data-ttu-id="201f1-123">На вкладке **Публикация** в окне **Публикация** нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="201f1-123">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Окно публикации в Visual Studio":::

## <a name="inspect-the-files"></a><span data-ttu-id="201f1-125">Проверка файлов</span><span class="sxs-lookup"><span data-stu-id="201f1-125">Inspect the files</span></span>

<span data-ttu-id="201f1-126">По умолчанию при публикации создается развертывание, зависящее от платформы. При таком развертывании опубликованное приложение выполняется на компьютере с установленной средой выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="201f1-126">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET runtime installed.</span></span> <span data-ttu-id="201f1-127">Пользователи могут запустить опубликованное приложение, дважды щелкнув исполняемый файл или выполнив команду `dotnet HelloWorld.dll` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="201f1-127">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="201f1-128">В следующих шагах будут рассмотрены файлы, созданные в процессе публикации.</span><span class="sxs-lookup"><span data-stu-id="201f1-128">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="201f1-129">В **обозревателе решений** выберите **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="201f1-129">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="201f1-130">В папке проекта разверните узел *bin/Release/net5.0/publish*.</span><span class="sxs-lookup"><span data-stu-id="201f1-130">In the project folder, expand *bin/Release/net5.0/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Опубликованные файлы в обозревателе решений":::

   <span data-ttu-id="201f1-132">Как показано на рисунке, опубликованные выходные данные включают следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="201f1-132">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="201f1-133">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="201f1-133">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="201f1-134">Это файл зависимостей среды выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-134">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="201f1-135">Он определяет библиотеки и компоненты .NET (включая библиотеку DLL, содержащую приложение), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-135">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="201f1-136">Дополнительные сведения см. в разделе [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (Файлы конфигурации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="201f1-136">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="201f1-137">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="201f1-137">*HelloWorld.dll*</span></span>

      <span data-ttu-id="201f1-138">Это версия [зависимого от платформы развертывания](../deploying/deploy-with-cli.md#framework-dependent-deployment) приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-138">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="201f1-139">Чтобы выполнить эту библиотеку динамической компоновки, введите `dotnet HelloWorld.dll` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="201f1-139">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="201f1-140">Этот метод запуска приложения работает на любой платформе, где установлена среда выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="201f1-140">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

   * <span data-ttu-id="201f1-141">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="201f1-141">*HelloWorld.exe*</span></span>

      <span data-ttu-id="201f1-142">Это версия [исполняемого, зависящего от платформы файла](../deploying/deploy-with-cli.md#framework-dependent-executable) приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-142">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="201f1-143">Чтобы запустить его, введите `HelloWorld.exe` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="201f1-143">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="201f1-144">Файл зависит от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="201f1-144">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="201f1-145">*HelloWorld.pdb* (необязателен для развертывания)</span><span class="sxs-lookup"><span data-stu-id="201f1-145">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="201f1-146">Это файл отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="201f1-146">This is the debug symbols file.</span></span> <span data-ttu-id="201f1-147">Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-147">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="201f1-148">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="201f1-148">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="201f1-149">Это файл конфигурации среды выполнения для приложения.</span><span class="sxs-lookup"><span data-stu-id="201f1-149">This is the application's run-time configuration file.</span></span> <span data-ttu-id="201f1-150">Он определяет версию платформы .NET, для которой предназначено приложение.</span><span class="sxs-lookup"><span data-stu-id="201f1-150">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="201f1-151">Кроме того, в него можно добавить параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="201f1-151">You can also add configuration options to it.</span></span> <span data-ttu-id="201f1-152">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="201f1-152">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="201f1-153">Запуск опубликованного приложения</span><span class="sxs-lookup"><span data-stu-id="201f1-153">Run the published app</span></span>

1. <span data-ttu-id="201f1-154">В **обозревателе решений** щелкните папку *publish* правой кнопкой мыши и выберите команду **Копировать полный путь**.</span><span class="sxs-lookup"><span data-stu-id="201f1-154">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="201f1-155">Откройте командную строку и перейдите к папке *publish*.</span><span class="sxs-lookup"><span data-stu-id="201f1-155">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="201f1-156">Для этого введите `cd` и вставьте полный путь.</span><span class="sxs-lookup"><span data-stu-id="201f1-156">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="201f1-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="201f1-157">For example:</span></span>

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="201f1-158">Запустите приложение с помощью исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="201f1-158">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="201f1-159">Введите `HelloWorld.exe` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="201f1-159">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="201f1-160">В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="201f1-160">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="201f1-161">Запустите приложение с помощью команды `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="201f1-161">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="201f1-162">Введите `dotnet HelloWorld.dll` и нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="201f1-162">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="201f1-163">В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="201f1-163">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="201f1-164">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="201f1-164">Additional resources</span></span>

- [<span data-ttu-id="201f1-165">развертывание приложений .NET</span><span class="sxs-lookup"><span data-stu-id="201f1-165">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="201f1-166">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="201f1-166">Next steps</span></span>

<span data-ttu-id="201f1-167">В этом руководстве вы опубликовали консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="201f1-167">In this tutorial, you published a console app.</span></span> <span data-ttu-id="201f1-168">Далее вы создадите библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="201f1-168">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="201f1-169">Создание библиотеки классов .NET с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="201f1-169">Create a .NET class library using Visual Studio</span></span>](library-with-visual-studio.md)
