---
title: Включение или отключение автоматически создаваемых перенаправлений привязок
description: Узнайте, как включить или отключить автоматическое перенаправление привязки. Эта функция влияет на классические приложения и веб-приложения, предназначенные для .NET Framework 4.5.1 или более поздней версии.
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: b099ab4958b1cf41b76884243e252e19a7a951b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698836"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="fd2d1-104">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="fd2d1-104">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="fd2d1-105">При компиляции приложений в Visual Studio, предназначенных для .NET Framework 4.5.1 и более поздних версий, перенаправления привязок могут быть автоматически добавлены в файл конфигурации приложения для переопределения унификации сборок.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-105">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="fd2d1-106">Переадресации привязок добавляются, если приложение или его компоненты ссылаются на несколько версий одной сборки, даже если вручную указать переадресации привязок в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-106">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="fd2d1-107">Функция автоматического перенаправления привязок влияет на классические приложения и веб-приложения, предназначенные для .NET Framework 4.5.1 или более поздней версии, хотя поведение немного отличается для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-107">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="fd2d1-108">Можно включить автоматическое перенаправление привязки, если у вас есть приложения, предназначенные для предыдущих версий .NET Framework, или отключить эту функцию, если необходимо вручную создать перенаправления привязок.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-108">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="fd2d1-109">Отключение автоматического перенаправления привязок в классических приложениях</span><span class="sxs-lookup"><span data-stu-id="fd2d1-109">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="fd2d1-110">Автоматические перенаправления привязок включены по умолчанию для классических приложений Windows, предназначенных для .NET Framework 4.5.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-110">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="fd2d1-111">Перенаправления привязки добавляются в файл конфигурации вывода (**app.config**) при компиляции приложения и переопределяют унификацию сборок, которая в противном случае может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-111">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="fd2d1-112">Исходный файл **app.config** не изменяется.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-112">The source **app.config** file is not modified.</span></span> <span data-ttu-id="fd2d1-113">Эту функцию можно отключить, изменив файл проекта для приложения или сняв флажок в свойствах проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-113">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="fd2d1-114">Отключить через свойства проекта</span><span class="sxs-lookup"><span data-stu-id="fd2d1-114">Disable through project properties</span></span>

<span data-ttu-id="fd2d1-115">При наличии Visual Studio 2017 версии 15,7 или более поздней можно легко отключить автоматически создаваемые перенаправления привязок на страницах свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-115">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="fd2d1-116">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-116">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="fd2d1-117">На странице **приложение** снимите флажок **Автоматическое создание перенаправлений привязки** .</span><span class="sxs-lookup"><span data-stu-id="fd2d1-117">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="fd2d1-118">Нажмите клавиши **CTRL** + **S** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-118">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="fd2d1-119">Отключение вручную в файле проекта</span><span class="sxs-lookup"><span data-stu-id="fd2d1-119">Disable manually in the project file</span></span>

1. <span data-ttu-id="fd2d1-120">Откройте файл проекта для редактирования с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="fd2d1-120">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="fd2d1-121">В Visual Studio выберите проект в **Обозреватель решений**, а затем в контекстном меню выберите **Открыть папку в проводнике** .</span><span class="sxs-lookup"><span data-stu-id="fd2d1-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="fd2d1-122">В проводнике найдите файл проекта (с расширением CSPROJ или VBPROJ) и откройте его в блокноте.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-122">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="fd2d1-123">В **Обозреватель решений** щелкните правой кнопкой мыши проект в Visual Studio и выберите команду **Выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-123">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="fd2d1-124">Снова щелкните правой кнопкой мыши выгруженный проект и выберите пункт **изменить [имя_проекта. csproj]**.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-124">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="fd2d1-125">Найдите в файле проекта следующую запись свойства:</span><span class="sxs-lookup"><span data-stu-id="fd2d1-125">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="fd2d1-126">Задайте для параметра `true` значение `false`:</span><span class="sxs-lookup"><span data-stu-id="fd2d1-126">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="fd2d1-127">Включение автоматического перенаправления привязок вручную</span><span class="sxs-lookup"><span data-stu-id="fd2d1-127">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="fd2d1-128">Можно включить автоматическое перенаправление привязок в существующих приложениях, предназначенных для более ранних версий .NET Framework, или в случаях, когда не будет автоматически предложено добавить перенаправление.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-128">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="fd2d1-129">Если вы нацелены на более новую версию платформы, но не получаете автоматически запрос на Добавление перенаправления, скорее всего, будут получены выходные данные сборки, предлагающие повторное сопоставление сборок.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-129">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="fd2d1-130">Откройте файл проекта для редактирования с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="fd2d1-130">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="fd2d1-131">В Visual Studio выберите проект в **Обозреватель решений**, а затем в контекстном меню выберите **Открыть папку в проводнике** .</span><span class="sxs-lookup"><span data-stu-id="fd2d1-131">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="fd2d1-132">В проводнике найдите файл проекта (с расширением CSPROJ или VBPROJ) и откройте его в блокноте.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-132">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="fd2d1-133">В **Обозреватель решений** щелкните правой кнопкой мыши проект в Visual Studio и выберите команду **Выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-133">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="fd2d1-134">Снова щелкните правой кнопкой мыши выгруженный проект и выберите пункт **изменить [имя_проекта. csproj]**.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-134">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="fd2d1-135">Добавьте следующий элемент в первую группу свойств конфигурации (под \<PropertyGroup> тегом):</span><span class="sxs-lookup"><span data-stu-id="fd2d1-135">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="fd2d1-136">Ниже приведен пример файла проекта с вставленным элементом:</span><span class="sxs-lookup"><span data-stu-id="fd2d1-136">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="fd2d1-137">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-137">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="fd2d1-138">Включение автоматического перенаправления привязок в веб-приложениях</span><span class="sxs-lookup"><span data-stu-id="fd2d1-138">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="fd2d1-139">Для веб-приложений автоматические переадресации привязок реализованы иным образом.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-139">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="fd2d1-140">Поскольку файл конфигурации источника (**web.config**) необходимо изменить для веб-приложений, перенаправления привязки не добавляются автоматически в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-140">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="fd2d1-141">Однако Visual Studio уведомляет вас о конфликтах привязки, и вы можете добавлять переадресации привязок для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-141">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="fd2d1-142">Поскольку вам всегда предлагается добавить перенаправления привязок, вам не нужно явно отключать эту функцию для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-142">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="fd2d1-143">Добавление перенаправлений привязок в файл **web.config** :</span><span class="sxs-lookup"><span data-stu-id="fd2d1-143">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="fd2d1-144">В Visual Studio скомпилируйте приложение и проверьте его на наличие предупреждений сборки.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-144">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="fd2d1-145">![Предупреждение сборки для конфликтов ссылок сборок](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="fd2d1-145">![Build warning for assembly reference conflicts](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="fd2d1-146">При наличии конфликтов привязки сборок выводится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-146">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="fd2d1-147">Дважды щелкните предупреждение или выберите предупреждение и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="fd2d1-147">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="fd2d1-148">Откроется диалоговое окно, которое позволяет автоматически добавлять необходимые перенаправления привязок в исходный файл **web.config** .</span><span class="sxs-lookup"><span data-stu-id="fd2d1-148">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="fd2d1-149">![Диалоговое окно разрешений для переадресации привязки](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="fd2d1-149">![Binding redirect permission dialog](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="fd2d1-150">См. также</span><span class="sxs-lookup"><span data-stu-id="fd2d1-150">See also</span></span>

- [<span data-ttu-id="fd2d1-151">\<bindingRedirect> Элемент</span><span class="sxs-lookup"><span data-stu-id="fd2d1-151">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="fd2d1-152">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="fd2d1-152">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
