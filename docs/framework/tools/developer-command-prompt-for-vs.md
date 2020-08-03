---
title: Командная строка разработчика для Visual Studio
description: Узнайте, как использовать командную строку разработчика для Visual Studio, которая облегчает работу со средствами .NET. Эта командная строка автоматически устанавливает определенные переменные среды.
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: 92416820f47cb778dfcc916b8626df4aa328814c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167171"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="f5b0e-104">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f5b0e-104">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="f5b0e-105">Командная строка разработчика для Visual Studio облегчает использование средств .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-105">Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="f5b0e-106">Это командная строка, которая автоматически устанавливает определенные переменные среды.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-106">It's a command prompt that automatically sets specific environment variables.</span></span> <span data-ttu-id="f5b0e-107">После открытия Командной строки разработчика, вы можете ввести команды для [средств платформы .NET Framework](index.md), например `ildasm` или `clrver`.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-107">After opening Developer Command Prompt, you can enter the commands for [.NET Framework tools](index.md) such as `ildasm` or `clrver`.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5b0e-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f5b0e-108">Prerequisites</span></span>

- [<span data-ttu-id="f5b0e-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f5b0e-109">Visual Studio 2019</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="f5b0e-110">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="f5b0e-110">Search for the command prompt on your machine</span></span>

<span data-ttu-id="f5b0e-111">В зависимости от версии Visual Studio, дополнительно установленных пакетов SDK и рабочих нагрузок может иметься несколько вариантов командных строк.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-111">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs and workloads you've installed.</span></span> <span data-ttu-id="f5b0e-112">Если приведенные ниже действия не работают, можно попробовать [найти файлы на компьютере вручную](#manually-locate-the-files-on-your-machine) или [запустить командную строку из Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f5b0e-112">If the following steps don't work, you can try to [manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [start the command prompt from inside Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="windows-10"></a><span data-ttu-id="f5b0e-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5b0e-113">Windows 10</span></span>

1. <span data-ttu-id="f5b0e-114">Выберите **Пуск** ![клавишу с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="f5b0e-114">Select **Start** ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="f5b0e-115">и прокрутите до буквы **V**.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-115">and scroll to the letter **V**.</span></span>

1. <span data-ttu-id="f5b0e-116">Разверните папку **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-116">Expand the **Visual Studio 2019** folder.</span></span>

1. <span data-ttu-id="f5b0e-117">Выберите элемент **Командная строка разработчика для VS 2019** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="f5b0e-117">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

   <span data-ttu-id="f5b0e-118">Или вы можете начать вводить имя командной строки в поле поиска на панели задач и выбрать нужный результат, поскольку список результатов начнет отображать найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-118">Alternatively, you can start typing the name of the command prompt in the search box on the taskbar, and choose the result you want as the result list starts to display the search matches.</span></span>

   ![GIF с анимацией, показывающий поведение поиска в Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a><span data-ttu-id="f5b0e-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f5b0e-120">Windows 8.1</span></span>

1. <span data-ttu-id="f5b0e-121">Перейдите на экран **Пуск**, нажав клавишу с логотипом Windows ![Клавиша с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="f5b0e-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="f5b0e-122">на клавиатуре, например.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-122">on your keyboard for example.</span></span>

1. <span data-ttu-id="f5b0e-123">На **начальном экране** нажмите **Ctrl**+**Tab**, чтобы открыть список **приложений**, а затем нажмите **V**. Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-123">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then press **V**. This brings up a list that includes all installed Visual Studio command prompts.</span></span>

1. <span data-ttu-id="f5b0e-124">Выберите элемент **Командная строка разработчика для VS 2019** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="f5b0e-124">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

### <a name="windows-7"></a><span data-ttu-id="f5b0e-125">Windows 7</span><span class="sxs-lookup"><span data-stu-id="f5b0e-125">Windows 7</span></span>

1. <span data-ttu-id="f5b0e-126">Выберите **Пуск** а затем разверните **Все программы**.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-126">Choose **Start** and then expand **All Programs**.</span></span>

1. <span data-ttu-id="f5b0e-127">Выберите **Visual Studio 2019** > **Инструменты Visual Studio** > **Командная строка разработчика для VS 2019**, или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-127">Choose **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt for VS 2019**, or the command prompt you want to use.</span></span>

   ![Меню "Пуск" в Windows 7 с выделенной командной строкой](./media/developer-command-prompt-for-vs/windows7-menu.png)

<span data-ttu-id="f5b0e-129">Если установлены другие пакеты SDK, например, [пакет SDK для Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущих версий](https://developer.microsoft.com/windows/downloads/sdk-archive), могут появиться дополнительные командные строки.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts.</span></span> <span data-ttu-id="f5b0e-130">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="f5b0e-131">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="f5b0e-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="f5b0e-132">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span></span> <span data-ttu-id="f5b0e-133">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-133">But if, for some reason, searching for the command prompt doesn't produce the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="f5b0e-134">Попробуйте найти имя файла командной строки, например, *VsDevCmd.bat*или перейдите в папку "Инструменты", например, *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (путь изменяется в соответствии с версией Visual Studio, выпуском и расположением установки).</span><span class="sxs-lookup"><span data-stu-id="f5b0e-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder, such as *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="start-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="f5b0e-135">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f5b0e-135">Start the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="f5b0e-136">Для более удобного доступа Командную строку разработчика или любую другую командную строку можно добавить в меню "Инструменты" в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-136">For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio.</span></span> <span data-ttu-id="f5b0e-137">Чтобы сделать средство доступным, добавьте его в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="f5b0e-138">Ниже приведены инструкции.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-138">Here are the steps:</span></span>

1. <span data-ttu-id="f5b0e-139">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-139">Open Visual Studio.</span></span>

1. <span data-ttu-id="f5b0e-140">В начальном окне выберите **Продолжить без кода**.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-140">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="f5b0e-141">В строке меню, выберите **Инструменты** > **Внешние Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-141">On the menu bar, choose **Tools** > **External Tools**.</span></span>

1. <span data-ttu-id="f5b0e-142">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-142">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="f5b0e-143">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-143">A new entry appears.</span></span>

1. <span data-ttu-id="f5b0e-144">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-144">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

1. <span data-ttu-id="f5b0e-145">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-145">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

1. <span data-ttu-id="f5b0e-146">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-146">In the **Arguments** field, specify where to find the specific command prompt you want to use, such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span></span> <span data-ttu-id="f5b0e-147">Эта команда запускает Командную строку разработчика, установленную вместе с Visual Studio 2019 Community.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-147">This command launches the Developer Command Prompt that's installed with Visual Studio 2019 Community.</span></span> <span data-ttu-id="f5b0e-148">Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-148">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

1. <span data-ttu-id="f5b0e-149">В поле **Исходный каталог** укажите каталог, в котором будет запускаться командная строка.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-149">In the **Initial directory** field, specify the directory in which the command prompt will start.</span></span> <span data-ttu-id="f5b0e-150">Выберите значение, например **Каталог проекта**, нажав стрелку рядом с полем.</span><span class="sxs-lookup"><span data-stu-id="f5b0e-150">Choose a value such as **Project Directory** by selecting the arrow next to the field.</span></span>

1. <span data-ttu-id="f5b0e-151">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="f5b0e-151">Choose the **OK** button.</span></span>

   ![Диалоговое окно "Внешние инструменты" с заполненными значениями полей.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   <span data-ttu-id="f5b0e-153">В меню добавляется новый пункт и командную строку можно вызвать из меню "Инструменты".</span><span class="sxs-lookup"><span data-stu-id="f5b0e-153">The new menu item is added, and you can access the command prompt from the Tools menu.</span></span>

   ![Пункт меню "Командная строка" в Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="f5b0e-155">См. также</span><span class="sxs-lookup"><span data-stu-id="f5b0e-155">See also</span></span>

- [<span data-ttu-id="f5b0e-156">Инструменты .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f5b0e-156">.NET Framework Tools</span></span>](index.md)
- [<span data-ttu-id="f5b0e-157">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="f5b0e-157">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
- [<span data-ttu-id="f5b0e-158">Использование набора инструментов C++ Microsoft из командной строки</span><span class="sxs-lookup"><span data-stu-id="f5b0e-158">Use the Microsoft C++ toolset from the command line</span></span>](/cpp/build/building-on-the-command-line)
