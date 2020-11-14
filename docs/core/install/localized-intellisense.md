---
title: Установка локализованных файлов IntelliSense
description: Узнайте, как настроить на компьютере разработки использование локализованных файлов IntelliSense для проектов .NET 5+ (включая .NET Core) в Visual Studio.
ms.date: 11/06/2020
ms.openlocfilehash: 45eeae12ca79179cacb3d48fca28118de70e0a4f
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506770"
---
# <a name="how-to-install-localized-intellisense-files-for-net"></a><span data-ttu-id="a62a8-103">Установка локализованных файлов IntelliSense для .NET</span><span class="sxs-lookup"><span data-stu-id="a62a8-103">How to install localized IntelliSense files for .NET</span></span>

<span data-ttu-id="a62a8-104">[IntelliSense](/visualstudio/ide/using-intellisense) — это вспомогательное средство для завершения кода, доступное в различных интегрированных средах разработки (IDE), таких как Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a62a8-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that's available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="a62a8-105">По умолчанию при разработке проектов .NET в пакет SDK входит только английская версия файлов IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a62a8-105">By default, when you're developing .NET projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="a62a8-106">В этой статье описано, как выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="a62a8-106">This article explains:</span></span>

- <span data-ttu-id="a62a8-107">Установка локализованной версии файлов.</span><span class="sxs-lookup"><span data-stu-id="a62a8-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="a62a8-108">Изменение установки Visual Studio для использования другого языка.</span><span class="sxs-lookup"><span data-stu-id="a62a8-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a62a8-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="a62a8-109">Prerequisites</span></span>

- <span data-ttu-id="a62a8-110">[Пакет SDK для .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) или более поздней версии, например [пакет SDK для .NET 5](https://dotnet.microsoft.com/download/dotnet/5.0).</span><span class="sxs-lookup"><span data-stu-id="a62a8-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version, such as [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0).</span></span>
- <span data-ttu-id="a62a8-111">[Visual Studio 2019 версии 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a62a8-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="a62a8-112">Скачивание и установка локализованных файлов IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a62a8-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a62a8-113">Эта процедура требует наличия прав администратора, чтобы копировать файлы IntelliSense в папку установки .NET.</span><span class="sxs-lookup"><span data-stu-id="a62a8-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET installation folder.</span></span>

1. <span data-ttu-id="a62a8-114">Перейдите на страницу [скачивания файлов IntelliSense](https://dotnet.microsoft.com/download/intellisense).</span><span class="sxs-lookup"><span data-stu-id="a62a8-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/intellisense) page.</span></span>

1. <span data-ttu-id="a62a8-115">Скачайте файл IntelliSense для нужных языка и версии.</span><span class="sxs-lookup"><span data-stu-id="a62a8-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="a62a8-116">Извлеките содержимое ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="a62a8-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="a62a8-117">Перейдите в папку IntelliSense для .NET.</span><span class="sxs-lookup"><span data-stu-id="a62a8-117">Navigate to the .NET Intellisense folder.</span></span>

   1. <span data-ttu-id="a62a8-118">Перейдите в папку установки .NET.</span><span class="sxs-lookup"><span data-stu-id="a62a8-118">Navigate to the .NET installation folder.</span></span> <span data-ttu-id="a62a8-119">Ее расположение по умолчанию: *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="a62a8-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="a62a8-120">Выберите пакет SDK, для которого необходимо установить IntelliSense, и перейдите по соответствующему пути.</span><span class="sxs-lookup"><span data-stu-id="a62a8-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="a62a8-121">Можно выбрать один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="a62a8-121">You have the following options:</span></span>

      | <span data-ttu-id="a62a8-122">Тип пакета SDK</span><span class="sxs-lookup"><span data-stu-id="a62a8-122">SDK type</span></span>              | <span data-ttu-id="a62a8-123">путь</span><span class="sxs-lookup"><span data-stu-id="a62a8-123">Path</span></span>                               |
      |-----------------------|------------------------------------|
      | <span data-ttu-id="a62a8-124">.NET версии 5 или выше и .NET Core</span><span class="sxs-lookup"><span data-stu-id="a62a8-124">.NET 5+ and .NET Core</span></span> | <span data-ttu-id="a62a8-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="a62a8-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="a62a8-126">Классические приложения</span><span class="sxs-lookup"><span data-stu-id="a62a8-126">Windows Desktop</span></span>       | <span data-ttu-id="a62a8-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="a62a8-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="a62a8-128">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="a62a8-128">.NET Standard</span></span>         | <span data-ttu-id="a62a8-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="a62a8-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="a62a8-130">Перейдите к версии, для которой необходимо установить локализованные файлы IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a62a8-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="a62a8-131">Например, *5.0.0*.</span><span class="sxs-lookup"><span data-stu-id="a62a8-131">For example, *5.0.0*.</span></span>
   1. <span data-ttu-id="a62a8-132">Откройте папку *ref*.</span><span class="sxs-lookup"><span data-stu-id="a62a8-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="a62a8-133">Откройте папку моникера.</span><span class="sxs-lookup"><span data-stu-id="a62a8-133">Open the moniker folder.</span></span> <span data-ttu-id="a62a8-134">Например: *net5.0*.</span><span class="sxs-lookup"><span data-stu-id="a62a8-134">For example, *net5.0*.</span></span>

   <span data-ttu-id="a62a8-135">Таким образом, полный путь для перехода будет выглядеть примерно так: *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.</span><span class="sxs-lookup"><span data-stu-id="a62a8-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.</span></span>

1. <span data-ttu-id="a62a8-136">В открытой папке моникера создайте вложенную папку.</span><span class="sxs-lookup"><span data-stu-id="a62a8-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="a62a8-137">Имя папки указывает, какой язык будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="a62a8-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="a62a8-138">В следующей таблице приводятся различные варианты.</span><span class="sxs-lookup"><span data-stu-id="a62a8-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="a62a8-139">Язык</span><span class="sxs-lookup"><span data-stu-id="a62a8-139">Language</span></span>              | <span data-ttu-id="a62a8-140">Имя папки</span><span class="sxs-lookup"><span data-stu-id="a62a8-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="a62a8-141">Португальский (Бразилия)</span><span class="sxs-lookup"><span data-stu-id="a62a8-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="a62a8-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="a62a8-142">*pt-br*</span></span>     |
   | <span data-ttu-id="a62a8-143">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="a62a8-143">Chinese (simplified)</span></span>  | <span data-ttu-id="a62a8-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="a62a8-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="a62a8-145">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="a62a8-145">Chinese (traditional)</span></span> | <span data-ttu-id="a62a8-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="a62a8-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="a62a8-147">Французский</span><span class="sxs-lookup"><span data-stu-id="a62a8-147">French</span></span>                | <span data-ttu-id="a62a8-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="a62a8-148">*fr*</span></span>        |
   | <span data-ttu-id="a62a8-149">Немецкий</span><span class="sxs-lookup"><span data-stu-id="a62a8-149">German</span></span>                | <span data-ttu-id="a62a8-150">*de*</span><span class="sxs-lookup"><span data-stu-id="a62a8-150">*de*</span></span>        |
   | <span data-ttu-id="a62a8-151">Итальянский</span><span class="sxs-lookup"><span data-stu-id="a62a8-151">Italian</span></span>               | <span data-ttu-id="a62a8-152">*it*</span><span class="sxs-lookup"><span data-stu-id="a62a8-152">*it*</span></span>        |
   | <span data-ttu-id="a62a8-153">Японский</span><span class="sxs-lookup"><span data-stu-id="a62a8-153">Japanese</span></span>              | <span data-ttu-id="a62a8-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="a62a8-154">*ja*</span></span>        |
   | <span data-ttu-id="a62a8-155">Корейский</span><span class="sxs-lookup"><span data-stu-id="a62a8-155">Korean</span></span>                | <span data-ttu-id="a62a8-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="a62a8-156">*ko*</span></span>        |
   | <span data-ttu-id="a62a8-157">Русский</span><span class="sxs-lookup"><span data-stu-id="a62a8-157">Russian</span></span>               | <span data-ttu-id="a62a8-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="a62a8-158">*ru*</span></span>        |
   | <span data-ttu-id="a62a8-159">Испанский</span><span class="sxs-lookup"><span data-stu-id="a62a8-159">Spanish</span></span>               | <span data-ttu-id="a62a8-160">*es*</span><span class="sxs-lookup"><span data-stu-id="a62a8-160">*es*</span></span>        |

1. <span data-ttu-id="a62a8-161">Скопируйте в эту новую папку файлы *.xml* , извлеченные на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a62a8-161">Copy the *.xml* files you extracted in step 3 to this new folder.</span></span> <span data-ttu-id="a62a8-162">Файлы *.xml* распределяются по папкам пакетов SDK, поэтому скопируйте их в соответствующий SDK, выбранный на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="a62a8-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose in step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="a62a8-163">Изменение языка Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a62a8-163">Modify Visual Studio language</span></span>

<span data-ttu-id="a62a8-164">Чтобы в Visual Studio использовать другой язык для IntelliSense, необходимо установить соответствующий языковой пакет.</span><span class="sxs-lookup"><span data-stu-id="a62a8-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="a62a8-165">Это можно сделать [во время установки](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) или позднее, изменив установку Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a62a8-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="a62a8-166">Если среда Visual Studio уже настроена с нужным вам языком, установка IntelliSense также будет готова.</span><span class="sxs-lookup"><span data-stu-id="a62a8-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="a62a8-167">Установка языкового пакета</span><span class="sxs-lookup"><span data-stu-id="a62a8-167">Install the language pack</span></span>

<span data-ttu-id="a62a8-168">Если нужный языковой пакет не был установлен, обновите Visual Studio, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a62a8-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a62a8-169">Чтобы установить, обновить или изменить среду Visual Studio, необходимо войти в учетную запись с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="a62a8-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="a62a8-170">Дополнительные сведения см. в статье [Разрешения пользователей и Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a62a8-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="a62a8-171">Найдите установщик Visual Studio на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="a62a8-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="a62a8-172">Например, на компьютере с Windows 10 нажмите кнопку **Пуск** и прокрутите список до буквы **V** , где расположен пункт **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-172">For example, on a computer running Windows 10, select **Start** , and then scroll to the letter **V** , where it's listed as **Visual Studio Installer**.</span></span>

   ![Открытие Visual Studio Installer в Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="a62a8-174">Кроме того, Visual Studio Installer можно найти в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="a62a8-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="a62a8-175">Для продолжения работы может потребоваться обновление самого установщика.</span><span class="sxs-lookup"><span data-stu-id="a62a8-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="a62a8-176">Если это так, следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="a62a8-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="a62a8-177">В установщике найдите установленный у вас выпуск Visual Studio, для которого нужно добавить языковой пакет, и щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Обновление или изменение Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="a62a8-179">Если кнопка **Изменить** отсутствует, но доступна кнопка **Обновить** , необходимо обновить Visual Studio и лишь затем изменить установку.</span><span class="sxs-lookup"><span data-stu-id="a62a8-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="a62a8-180">После завершения обновления должна появиться кнопка **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="a62a8-181">На вкладке **Языковые пакеты** выберите языки, которые нужно установить, или отмените выбор тех, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="a62a8-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Вкладка "Языковые пакеты" в Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="a62a8-183">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-183">Choose **Modify**.</span></span> <span data-ttu-id="a62a8-184">Начнется обновление.</span><span class="sxs-lookup"><span data-stu-id="a62a8-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="a62a8-185">Изменение языковых параметров в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a62a8-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="a62a8-186">После установки нужных языковых пакетов измените параметры Visual Studio для использования другого языка, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="a62a8-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="a62a8-187">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a62a8-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="a62a8-188">В начальном окне выберите **Продолжить без кода**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="a62a8-189">В строке меню выберите **Сервис** > **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="a62a8-190">Откроется диалоговое окно "Параметры ".</span><span class="sxs-lookup"><span data-stu-id="a62a8-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="a62a8-191">В узле **Среда** выберите **Выбор языка**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="a62a8-192">В раскрывающемся списке **Язык** выберите язык.</span><span class="sxs-lookup"><span data-stu-id="a62a8-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="a62a8-193">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-193">Choose **OK**.</span></span>

1. <span data-ttu-id="a62a8-194">Появится диалоговое окно, информирующее о необходимости перезапуска Visual Studio для применения изменений.</span><span class="sxs-lookup"><span data-stu-id="a62a8-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="a62a8-195">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a62a8-195">Choose **OK**.</span></span>

1. <span data-ttu-id="a62a8-196">Перезапустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a62a8-196">Restart Visual Studio.</span></span>

<span data-ttu-id="a62a8-197">Теперь при открытии проекта .NET, предназначенного для версии только что установленных файлов IntelliSense, функции IntelliSense должны работать надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="a62a8-197">After this, your IntelliSense should work as expected when you open a .NET project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a62a8-198">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a62a8-198">See also</span></span>

- [<span data-ttu-id="a62a8-199">IntelliSense в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a62a8-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
