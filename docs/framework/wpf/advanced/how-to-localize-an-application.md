---
title: Локализация приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209686"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="9409b-102">Как локализовать приложение</span><span class="sxs-lookup"><span data-stu-id="9409b-102">How to: Localize an application</span></span>

<span data-ttu-id="9409b-103">В этом учебнике рассматривается создание локализованного приложения с помощью средства LocBaml.</span><span class="sxs-lookup"><span data-stu-id="9409b-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9409b-104">Средство LocBaml не является готовым приложением.</span><span class="sxs-lookup"><span data-stu-id="9409b-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="9409b-105">Оно представлено в качестве примера, в котором используются некоторые API локализации и показывается, как можно написать средство локализации.</span><span class="sxs-lookup"><span data-stu-id="9409b-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="9409b-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="9409b-106">Overview</span></span>

<span data-ttu-id="9409b-107">Эта статья содержит пошаговый подход к локализации приложения.</span><span class="sxs-lookup"><span data-stu-id="9409b-107">This article gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="9409b-108">Сначала необходимо подготовить приложение, чтобы можно было извлечь текст, который будет преобразован.</span><span class="sxs-lookup"><span data-stu-id="9409b-108">First, you prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="9409b-109">После перевода текста выполняется слияние переведенного текста в новую копию исходного приложения.</span><span class="sxs-lookup"><span data-stu-id="9409b-109">After the text is translated, you merge the translated text into a new copy of the original application.</span></span>
  
## <a name="create-a-sample-application"></a><span data-ttu-id="9409b-110">Создание примера приложения</span><span class="sxs-lookup"><span data-stu-id="9409b-110">Create a sample application</span></span>

<span data-ttu-id="9409b-111">На этом шаге вы подготовите приложение к локализации.</span><span class="sxs-lookup"><span data-stu-id="9409b-111">In this step, you prepare your app for localization.</span></span> <span data-ttu-id="9409b-112">В примерах Windows Presentation Foundation (WPF) предоставляется образец HelloApp, который будет использоваться для примеров кода в этом обсуждении.</span><span class="sxs-lookup"><span data-stu-id="9409b-112">In the Windows Presentation Foundation (WPF) samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="9409b-113">Если вы хотите использовать этот пример, Скачайте файлы XAML (XAML) из [примера средства LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="9409b-113">If you would like to use this sample, download the Extensible Application Markup Language (XAML) files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="9409b-114">Разработайте свое приложение до точки, в которой хотите начать локализацию.</span><span class="sxs-lookup"><span data-stu-id="9409b-114">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="9409b-115">Укажите язык разработки в файле проекта, чтобы MSBuild создавал основную сборку и вспомогательную сборку (файл с расширением Resources. dll) для хранения нейтральных языковых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9409b-115">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="9409b-116">Файл проекта в примере HelloApp — HelloApp.csproj.</span><span class="sxs-lookup"><span data-stu-id="9409b-116">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="9409b-117">В этом файле можно найти язык разработки, заданный следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9409b-117">In that file, you will find the development language identified as follows:</span></span>  
  
   `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="9409b-118">Добавьте идентификаторы UID в файлы XAML.</span><span class="sxs-lookup"><span data-stu-id="9409b-118">Add Uids to your XAML files.</span></span> <span data-ttu-id="9409b-119">ИД пользователей используются для отслеживания изменений в файлах и для идентификации элементов, которые должны быть переведены.</span><span class="sxs-lookup"><span data-stu-id="9409b-119">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="9409b-120">Чтобы добавить ИД пользователей в файлы, выполните `updateuid` команду в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="9409b-120">To add Uids to your files, run `updateuid` on your project file:</span></span>  

   `msbuild -t:updateuid helloapp.csproj`

   <span data-ttu-id="9409b-121">Чтобы убедиться в отсутствии отсутствующих или повторяющихся ИД UID, выполните `checkuid` :</span><span class="sxs-lookup"><span data-stu-id="9409b-121">To verify that you have no missing or duplicate Uids, run `checkuid`:</span></span>  

   `msbuild -t:checkuid helloapp.csproj`

   <span data-ttu-id="9409b-122">После выполнения `updateuid` файлы должны содержать идентификаторы UID.</span><span class="sxs-lookup"><span data-stu-id="9409b-122">After running `updateuid`, your files should contain Uids.</span></span> <span data-ttu-id="9409b-123">Например, в файле *Pane1. XAML* для HelloApp необходимо найти следующее:</span><span class="sxs-lookup"><span data-stu-id="9409b-123">For example, in the *Pane1.xaml* file of HelloApp, you should find the following:</span></span>  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="9409b-124">Создание вспомогательной сборки ресурсов нейтрального языка</span><span class="sxs-lookup"><span data-stu-id="9409b-124">Create the neutral-language resources satellite assembly</span></span>

<span data-ttu-id="9409b-125">После настройки приложения для создания вспомогательной сборки ресурсов нейтрального языка создается приложение.</span><span class="sxs-lookup"><span data-stu-id="9409b-125">After the application is configured to generate a neutral-language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="9409b-126">При этом создается основная сборка приложения, а также вспомогательная сборка ресурсов нейтрального языка, необходимая LocBaml для локализации.</span><span class="sxs-lookup"><span data-stu-id="9409b-126">This generates the main application assembly as well as the neutral-language resources satellite assembly that's required by LocBaml for localization.</span></span>

<span data-ttu-id="9409b-127">Чтобы создать приложение:</span><span class="sxs-lookup"><span data-stu-id="9409b-127">To build the application:</span></span>  
  
1. <span data-ttu-id="9409b-128">Скомпилируйте HelloApp, чтобы создать библиотеку динамической компоновки (DLL):</span><span class="sxs-lookup"><span data-stu-id="9409b-128">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
   `msbuild helloapp.csproj`
  
2. <span data-ttu-id="9409b-129">Только что созданная основная сборка приложения HelloApp. exe создается в следующей папке: *к:\хеллоапп\бин\дебуг*</span><span class="sxs-lookup"><span data-stu-id="9409b-129">The newly created main application assembly, HelloApp.exe, is created in the following folder: *C:\HelloApp\Bin\Debug*</span></span>
  
3. <span data-ttu-id="9409b-130">Вновь созданная вспомогательная сборка ресурсов нейтрального языка, HelloApp. Resources. dll, создается в следующей папке: *к:\хеллоапп\бин\дебуг\ен-ус*</span><span class="sxs-lookup"><span data-stu-id="9409b-130">The newly created neutral-language resources satellite assembly, HelloApp.resources.dll, is created in the following folder: *C:\HelloApp\Bin\Debug\en-US*</span></span>
  
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="9409b-131">Построение средства LocBaml</span><span class="sxs-lookup"><span data-stu-id="9409b-131">Build the LocBaml tool</span></span>  
  
1. <span data-ttu-id="9409b-132">Все файлы, необходимые для построения LocBaml, находятся в примерах WPF.</span><span class="sxs-lookup"><span data-stu-id="9409b-132">All the files necessary to build LocBaml are located in the WPF samples.</span></span> <span data-ttu-id="9409b-133">Скачайте файлы C# из [примера средства LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="9409b-133">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="9409b-134">Из командной строки запустите файл проекта (locbaml.csproj), чтобы построить это средство:</span><span class="sxs-lookup"><span data-stu-id="9409b-134">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  

   `msbuild locbaml.csproj`
  
3. <span data-ttu-id="9409b-135">Перейдите в каталог *Bin\Release* , чтобы найти только что созданный исполняемый файл (LocBaml. exe).</span><span class="sxs-lookup"><span data-stu-id="9409b-135">Go to the *Bin\Release* directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="9409b-136">Пример: *к:\локбамл\бин\релеасе\локбамл.ЕКСЕ*</span><span class="sxs-lookup"><span data-stu-id="9409b-136">Example: *C:\LocBaml\Bin\Release\locbaml.exe*</span></span>
  
4. <span data-ttu-id="9409b-137">При запуске LocBaml можно указать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="9409b-137">The options that you can specify when you run LocBaml are as follows.</span></span>

   | <span data-ttu-id="9409b-138">Параметр</span><span class="sxs-lookup"><span data-stu-id="9409b-138">Option</span></span> | <span data-ttu-id="9409b-139">Описание</span><span class="sxs-lookup"><span data-stu-id="9409b-139">Description</span></span>|
   | - | - |
   | <span data-ttu-id="9409b-140">`parse` или `-p`</span><span class="sxs-lookup"><span data-stu-id="9409b-140">`parse` or `-p`</span></span> | <span data-ttu-id="9409b-141">Анализирует файлы BAML, Resources или DLL для создания файла CSV или txt.</span><span class="sxs-lookup"><span data-stu-id="9409b-141">Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span> |
   | <span data-ttu-id="9409b-142">`generate` или `-g`</span><span class="sxs-lookup"><span data-stu-id="9409b-142">`generate` or `-g`</span></span> | <span data-ttu-id="9409b-143">Создает локализованный двоичный файл с помощью переведенного файла.</span><span class="sxs-lookup"><span data-stu-id="9409b-143">Generates a localized binary file by using a translated file.</span></span> |
   | <span data-ttu-id="9409b-144">`out`или `-o` {*филедиректори*]</span><span class="sxs-lookup"><span data-stu-id="9409b-144">`out` or `-o` {*filedirectory*]</span></span> | <span data-ttu-id="9409b-145">Имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="9409b-145">Output file name.</span></span> |
   | <span data-ttu-id="9409b-146">`culture`или `-cul` {*culture*]</span><span class="sxs-lookup"><span data-stu-id="9409b-146">`culture` or `-cul` {*culture*]</span></span> | <span data-ttu-id="9409b-147">Языковой стандарт для выходных сборок.</span><span class="sxs-lookup"><span data-stu-id="9409b-147">Locale of output assemblies.</span></span> |
   | <span data-ttu-id="9409b-148">`translation`или `-trans` {*Translation. csv*]</span><span class="sxs-lookup"><span data-stu-id="9409b-148">`translation` or `-trans` {*translation.csv*]</span></span> | <span data-ttu-id="9409b-149">Переведенный или локализованный файл.</span><span class="sxs-lookup"><span data-stu-id="9409b-149">Translated or localized file.</span></span> |
   | <span data-ttu-id="9409b-150">`asmpath`или `-asmpath` {*филедиректори*]</span><span class="sxs-lookup"><span data-stu-id="9409b-150">`asmpath` or `-asmpath` {*filedirectory*]</span></span> | <span data-ttu-id="9409b-151">Если код XAML содержит пользовательские элементы управления, необходимо предоставить его `asmpath` сборке пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9409b-151">If your XAML code contains custom controls, you must supply the `asmpath` to the custom control assembly.</span></span> |
   | `nologo` | <span data-ttu-id="9409b-152"> запрещает отображение логотипа или сведений об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="9409b-152">Displays no logo or copyright information.</span></span> |
   | `verbose` | <span data-ttu-id="9409b-153"> отображает сведения режима подробного протоколирования.</span><span class="sxs-lookup"><span data-stu-id="9409b-153">Displays verbose mode information.</span></span> |
  
   > [!NOTE]
   > <span data-ttu-id="9409b-154">Если при запуске средства требуется список параметров, введите `LocBaml.exe` и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="9409b-154">If you need a list of the options when you are running the tool, enter `LocBaml.exe` and then press **Enter**.</span></span>
  
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="9409b-155">Использование LocBaml для синтаксического анализа файла</span><span class="sxs-lookup"><span data-stu-id="9409b-155">Use LocBaml to parse a file</span></span>

<span data-ttu-id="9409b-156">Теперь, после создания средства LocBaml, вы можете выполнить анализ файла HelloApp.resources.dll, чтобы извлечь текстовое содержимое, которое будет локализовано.</span><span class="sxs-lookup"><span data-stu-id="9409b-156">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="9409b-157">Скопируйте LocBaml.exe в папку приложения bin\debug, где была создана основная сборка приложения.</span><span class="sxs-lookup"><span data-stu-id="9409b-157">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="9409b-158">Чтобы выполнить анализ файла вспомогательной сборки и сохранить результат в виде CSV-файла, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9409b-158">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > <span data-ttu-id="9409b-159">Если входной файл HelloApp.resources.dll не находится в том же каталоге, что и LocBaml.exe, переместите один из файлов таким образом, чтобы оба файла были в одном каталоге.</span><span class="sxs-lookup"><span data-stu-id="9409b-159">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="9409b-160">При выполнении анализа файлов с помощью LocBaml выходные данные состоят из семи полей, разделенных запятыми (CSV-файлы) или знаками табуляции (TXT-файлы).</span><span class="sxs-lookup"><span data-stu-id="9409b-160">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="9409b-161">Ниже показан проанализированный CSV-файл для HelloApp.resources.dll:</span><span class="sxs-lookup"><span data-stu-id="9409b-161">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="9409b-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="9409b-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="9409b-163">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="9409b-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="9409b-164">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="9409b-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="9409b-165">Это следующие семь полей.</span><span class="sxs-lookup"><span data-stu-id="9409b-165">The seven fields are:</span></span>  
  
   - <span data-ttu-id="9409b-166">**Имя BAML**.</span><span class="sxs-lookup"><span data-stu-id="9409b-166">**BAML Name**.</span></span> <span data-ttu-id="9409b-167">Имя ресурса BAML по отношению к вспомогательной сборке исходного языка.</span><span class="sxs-lookup"><span data-stu-id="9409b-167">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   - <span data-ttu-id="9409b-168">**Ключ ресурса**.</span><span class="sxs-lookup"><span data-stu-id="9409b-168">**Resource Key**.</span></span> <span data-ttu-id="9409b-169">Идентификатор локализованного ресурса.</span><span class="sxs-lookup"><span data-stu-id="9409b-169">The localized resource identifier.</span></span>  
  
   - <span data-ttu-id="9409b-170">**Категория**.</span><span class="sxs-lookup"><span data-stu-id="9409b-170">**Category**.</span></span> <span data-ttu-id="9409b-171">Тип значения.</span><span class="sxs-lookup"><span data-stu-id="9409b-171">The value type.</span></span> <span data-ttu-id="9409b-172">См. раздел [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="9409b-172">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="9409b-173">**Удобочитаемость**.</span><span class="sxs-lookup"><span data-stu-id="9409b-173">**Readability**.</span></span> <span data-ttu-id="9409b-174">Может ли значение быть прочитано средством локализации.</span><span class="sxs-lookup"><span data-stu-id="9409b-174">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="9409b-175">См. раздел [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="9409b-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="9409b-176">**Изменяемость**.</span><span class="sxs-lookup"><span data-stu-id="9409b-176">**Modifiability**.</span></span> <span data-ttu-id="9409b-177">Может ли значение изменяться средством локализации.</span><span class="sxs-lookup"><span data-stu-id="9409b-177">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="9409b-178">См. раздел [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="9409b-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="9409b-179">**Комментарии**.</span><span class="sxs-lookup"><span data-stu-id="9409b-179">**Comments**.</span></span> <span data-ttu-id="9409b-180">Дополнительное описание значения, помогающее определить способ локализации значения.</span><span class="sxs-lookup"><span data-stu-id="9409b-180">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="9409b-181">См. раздел [атрибуты и комментарии локализации](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="9409b-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="9409b-182">**Значение**.</span><span class="sxs-lookup"><span data-stu-id="9409b-182">**Value**.</span></span> <span data-ttu-id="9409b-183">Текстовое значение для перевода на нужный язык.</span><span class="sxs-lookup"><span data-stu-id="9409b-183">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="9409b-184">В следующей таблице показывается, как эти поля соответствуют разделенным значениям CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="9409b-184">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="9409b-185">Имя BAML</span><span class="sxs-lookup"><span data-stu-id="9409b-185">BAML name</span></span>|<span data-ttu-id="9409b-186">Ключ ресурса</span><span class="sxs-lookup"><span data-stu-id="9409b-186">Resource key</span></span>|<span data-ttu-id="9409b-187">Категория</span><span class="sxs-lookup"><span data-stu-id="9409b-187">Category</span></span>|<span data-ttu-id="9409b-188">Удобочитаемость</span><span class="sxs-lookup"><span data-stu-id="9409b-188">Readability</span></span>|<span data-ttu-id="9409b-189">Изменяемость</span><span class="sxs-lookup"><span data-stu-id="9409b-189">Modifiability</span></span>|<span data-ttu-id="9409b-190">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9409b-190">Comments</span></span>|<span data-ttu-id="9409b-191">Значение</span><span class="sxs-lookup"><span data-stu-id="9409b-191">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="9409b-192">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="9409b-192">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="9409b-193">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="9409b-193">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="9409b-194">Игнорировать</span><span class="sxs-lookup"><span data-stu-id="9409b-194">Ignore</span></span>|<span data-ttu-id="9409b-195">Ложь.</span><span class="sxs-lookup"><span data-stu-id="9409b-195">FALSE</span></span>|<span data-ttu-id="9409b-196">Ложь.</span><span class="sxs-lookup"><span data-stu-id="9409b-196">FALSE</span></span>||<span data-ttu-id="9409b-197">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="9409b-197">#Text1;#Text2</span></span>|
   |<span data-ttu-id="9409b-198">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="9409b-198">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="9409b-199">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="9409b-199">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="9409b-200">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9409b-200">None</span></span>|<span data-ttu-id="9409b-201">TRUE</span><span class="sxs-lookup"><span data-stu-id="9409b-201">TRUE</span></span>|<span data-ttu-id="9409b-202">TRUE</span><span class="sxs-lookup"><span data-stu-id="9409b-202">TRUE</span></span>||<span data-ttu-id="9409b-203">Hello World</span><span class="sxs-lookup"><span data-stu-id="9409b-203">Hello World</span></span>|
   |<span data-ttu-id="9409b-204">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="9409b-204">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="9409b-205">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="9409b-205">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="9409b-206">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9409b-206">None</span></span>|<span data-ttu-id="9409b-207">TRUE</span><span class="sxs-lookup"><span data-stu-id="9409b-207">TRUE</span></span>|<span data-ttu-id="9409b-208">TRUE</span><span class="sxs-lookup"><span data-stu-id="9409b-208">TRUE</span></span>||<span data-ttu-id="9409b-209">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="9409b-209">Goodbye World</span></span>|
  
   <span data-ttu-id="9409b-210">Обратите внимание, что все значения поля **Comments** не содержат значений. Если поле не имеет значения, оно пустое.</span><span class="sxs-lookup"><span data-stu-id="9409b-210">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="9409b-211">Также обратите внимание, что элемент в первой строке не является ни читаемым, ни изменяемым, а параметр **Category** имеет значение "ignore", а все это означает, что значение не локализуется.</span><span class="sxs-lookup"><span data-stu-id="9409b-211">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="9409b-212">Чтобы упростить обнаружение локализуемых элементов в проанализированных файлах, особенно в больших файлах, можно сортировать или фильтровать элементы по **категориям**, **удобочитаемости**и **изменению**.</span><span class="sxs-lookup"><span data-stu-id="9409b-212">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="9409b-213">Например можно отфильтровать нечитаемые и неизменяемые значения.</span><span class="sxs-lookup"><span data-stu-id="9409b-213">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
## <a name="translate-the-localizable-content"></a><span data-ttu-id="9409b-214">Перевод локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="9409b-214">Translate the localizable content</span></span>

<span data-ttu-id="9409b-215">Используйте любое доступное средство для перевода извлеченного содержимого.</span><span class="sxs-lookup"><span data-stu-id="9409b-215">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="9409b-216">Хорошим способом этого является запись ресурсов в CSV-файл и их просмотр в Microsoft Excel, что приводит к изменению перевода на последний столбец (значение).</span><span class="sxs-lookup"><span data-stu-id="9409b-216">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="9409b-217">Использование LocBaml для создания нового файла. Resources. dll</span><span class="sxs-lookup"><span data-stu-id="9409b-217">Use LocBaml to generate a new .resources.dll file</span></span>

<span data-ttu-id="9409b-218">Содержимое, которое было идентифицировано при анализе файла HelloApp.resources.dll с помощью LocBaml, переведено, и его необходимо влить обратно в исходное приложение.</span><span class="sxs-lookup"><span data-stu-id="9409b-218">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="9409b-219">Используйте `generate` параметр или `-g` для создания нового файла Resources. dll.</span><span class="sxs-lookup"><span data-stu-id="9409b-219">Use the `generate` or `-g` option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="9409b-220">Чтобы создать новый файл HelloApp.resources.dll, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9409b-220">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="9409b-221">Пометьте язык и региональные параметры как en-US (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="9409b-221">Mark the culture as en-US (/cul:en-US).</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > <span data-ttu-id="9409b-222">Если входной файл Hello.csv не находится в том же каталоге, что и исполняемый файл LocBaml.exe, переместите один из файлов таким образом, чтобы оба файла были в одном каталоге.</span><span class="sxs-lookup"><span data-stu-id="9409b-222">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="9409b-223">Замените старый файл *HelloApp. Resources. dll* в каталоге *к:\хеллоапп\бин\дебуг\ен-ус\хеллоапп.ресаурцес.длл* на созданный файл *HelloApp. Resources. dll* .</span><span class="sxs-lookup"><span data-stu-id="9409b-223">Replace the old *HelloApp.resources.dll* file in the *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* directory with your newly created *HelloApp.resources.dll* file.</span></span>  
  
3. <span data-ttu-id="9409b-224">Теперь в вашем приложении фразы Hello World и Goodbye World должны быть переведены.</span><span class="sxs-lookup"><span data-stu-id="9409b-224">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="9409b-225">Для перевода на другой язык используйте язык, на который вы переводите.</span><span class="sxs-lookup"><span data-stu-id="9409b-225">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="9409b-226">В следующем примере показано, как переводить на канадский французский.</span><span class="sxs-lookup"><span data-stu-id="9409b-226">The following example shows how to translate to French-Canadian:</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. <span data-ttu-id="9409b-227">В той же основной сборке приложения создайте новую папку для выбранного языка и региональных параметров, в которой будет размещена новая вспомогательная сборка.</span><span class="sxs-lookup"><span data-stu-id="9409b-227">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="9409b-228">Для канадского французского папку можно назвать fr-CA.</span><span class="sxs-lookup"><span data-stu-id="9409b-228">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="9409b-229">Скопируйте созданную вспомогательную сборку в новую папку.</span><span class="sxs-lookup"><span data-stu-id="9409b-229">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="9409b-230">Чтобы протестировать новую вспомогательную сборку, необходимо изменить язык и региональные параметры, с которыми будет выполняться приложение.</span><span class="sxs-lookup"><span data-stu-id="9409b-230">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="9409b-231">Это можно сделать одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="9409b-231">You can do this in one of two ways:</span></span>  
  
   - <span data-ttu-id="9409b-232">Измените региональные параметры операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9409b-232">Change your operating system's regional settings.</span></span>
  
   - <span data-ttu-id="9409b-233">В своем приложении добавьте в файл App.xaml.cs следующий код:</span><span class="sxs-lookup"><span data-stu-id="9409b-233">In your application, add the following code to App.xaml.cs:</span></span>  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a><span data-ttu-id="9409b-234">Советы по использованию LocBaml</span><span class="sxs-lookup"><span data-stu-id="9409b-234">Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="9409b-235">Все зависимые сборки, которые определяют пользовательские элементы управления, должны быть скопированы в локальный каталог LocBaml или установлены в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="9409b-235">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="9409b-236">Это необходимо, поскольку API локализации должен иметь доступ к зависимым сборкам при чтении двоичного кода XAML (BAML).</span><span class="sxs-lookup"><span data-stu-id="9409b-236">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="9409b-237">Если основная сборка имеет подпись, созданная библиотека DLL ресурсов также должна быть подписана для ее загрузки.</span><span class="sxs-lookup"><span data-stu-id="9409b-237">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="9409b-238">Версия библиотеки DLL локализованных ресурсов должна быть синхронизирована с основной сборкой.</span><span class="sxs-lookup"><span data-stu-id="9409b-238">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9409b-239">См. также</span><span class="sxs-lookup"><span data-stu-id="9409b-239">See also</span></span>

- [<span data-ttu-id="9409b-240">Глобализация для WPF</span><span class="sxs-lookup"><span data-stu-id="9409b-240">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="9409b-241">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="9409b-241">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
