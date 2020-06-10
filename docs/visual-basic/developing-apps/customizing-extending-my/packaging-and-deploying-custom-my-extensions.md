---
title: Упаковка и развертывание пользовательских расширений пространства имен My
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 6d2cc2b01b04b30bd3b1a4371352ded20ea8664b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411757"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="d3d95-102">Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3d95-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="d3d95-103">Visual Basic позволяет легко развернуть пользовательские расширения для пространства имен `My` с помощью шаблонов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3d95-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="d3d95-104">Если вы создаете шаблон проекта, в котором расширения `My` являются неотъемлемой частью нового типа проекта, можно просто включить в проект собственный код расширения `My` при экспорте шаблона.</span><span class="sxs-lookup"><span data-stu-id="d3d95-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="d3d95-105">Дополнительные сведения об экспорте шаблонов проектов приведены в [руководстве по созданию шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="d3d95-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="d3d95-106">Если пользовательское расширение `My` представляет собой один файл кода, этот файл можно экспортировать как шаблон элемента, который пользователи смогут добавлять в проекты Visual Basic любого типа.</span><span class="sxs-lookup"><span data-stu-id="d3d95-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="d3d95-107">Позже вы сможете дополнить этот шаблон элемента новыми возможностями и действиями через пользовательское расширение `My` в проекте Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3d95-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="d3d95-108">Вот несколько примеров таких возможностей:</span><span class="sxs-lookup"><span data-stu-id="d3d95-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="d3d95-109">Предоставление пользователям возможности управлять настраиваемым расширением `My` через страницу **Расширения My** в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3d95-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="d3d95-110">Автоматическое добавление настраиваемого расширения `My` при добавлении в проект ссылок на конкретную сборку.</span><span class="sxs-lookup"><span data-stu-id="d3d95-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="d3d95-111">Удаление расширения `My` из списка элементов проекта, который отображается для шаблона элемента в диалоговом окне **Добавление элемента**.</span><span class="sxs-lookup"><span data-stu-id="d3d95-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="d3d95-112">В этой статье описано, как упаковать настраиваемое расширение `My` в качестве скрытого шаблона элемента, управление которым осуществляется на странице **Расширения My** в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3d95-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d3d95-113">Настраиваемое расширение `My` можно автоматически добавлять в проект одновременно со ссылкой на конкретную сборку.</span><span class="sxs-lookup"><span data-stu-id="d3d95-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="d3d95-114">Создание расширения пространства имен My</span><span class="sxs-lookup"><span data-stu-id="d3d95-114">Create a My namespace extension</span></span>

<span data-ttu-id="d3d95-115">Первым шагом при создании пакета развертывания для настраиваемого расширения `My` будет создание расширения в формате одного файла кода.</span><span class="sxs-lookup"><span data-stu-id="d3d95-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="d3d95-116">Дополнительные сведения и рекомендации по созданию настраиваемого расширения `My` см. в статье [Расширение пространства имен My в Visual Basic](extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d3d95-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="d3d95-117">Экспорт расширения пространства имен My в виде шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="d3d95-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="d3d95-118">Создав файл кода, который содержит расширение пространства имен `My`, вы сможете экспортировать этот файл кода как шаблон элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3d95-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="d3d95-119">Инструкции по экспорту файла в формате шаблона элемента Visual Studio см. в [руководстве по созданию шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="d3d95-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="d3d95-120">Если это расширение пространства имен `My` содержит зависимости от конкретной сборки, вы можете изменить шаблон элемента таким образом, чтобы расширение пространства имен `My` автоматически устанавливалось при добавлении соответствующей сборки.</span><span class="sxs-lookup"><span data-stu-id="d3d95-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="d3d95-121">Это позволит вам исключить ссылку на эту сборку при экспорте файла кода в виде шаблона элемента Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3d95-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="d3d95-122">Настройка шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="d3d95-122">Customize the item template</span></span>

<span data-ttu-id="d3d95-123">Вы можете разрешить управление шаблоном элемента через страницу **Расширения My** в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3d95-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d3d95-124">Можно также автоматически добавлять шаблон элемента в проект одновременно со ссылкой на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="d3d95-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="d3d95-125">Чтобы поддерживать такую настройку, потребуется добавить в шаблон новый файл CustomData, а затем добавить новый элемент в XML-код файла с расширением .vstemplate.</span><span class="sxs-lookup"><span data-stu-id="d3d95-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="d3d95-126">Добавление файла CustomData</span><span class="sxs-lookup"><span data-stu-id="d3d95-126">Add the CustomData file</span></span>

<span data-ttu-id="d3d95-127">Файл CustomData — это текстовый файл с расширением .CustomData (ему можно присвоить любое имя, имеющее смысл в контексте шаблона) и содержимым в формате XML.</span><span class="sxs-lookup"><span data-stu-id="d3d95-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="d3d95-128">XML-код в файле CustomData сообщает Visual Basic, что нужно включать расширение `My`, когда пользователи открывают страницу **Расширения My** в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3d95-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d3d95-129">Вы также можете добавить в XML-код файла CustomData необязательный атрибут <`AssemblyFullName>`.</span><span class="sxs-lookup"><span data-stu-id="d3d95-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="d3d95-130">В этом случае Visual Basic будет автоматически устанавливать настраиваемое расширение `My` при добавлении в проект ссылки на конкретную сборку.</span><span class="sxs-lookup"><span data-stu-id="d3d95-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="d3d95-131">Вы можете создать файл CustomData в любом текстовом редакторе или XML-редакторе, а затем разместить этот файл в сжатой папке шаблона элемента (ZIP-файле).</span><span class="sxs-lookup"><span data-stu-id="d3d95-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="d3d95-132">Например, следующий XML-код для файла CustomData будет добавлять элемент шаблона в папку My Extensions проекта Visual Basic при добавлении в проект ссылки на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll.</span><span class="sxs-lookup"><span data-stu-id="d3d95-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="d3d95-133">Файл CustomData содержит элемент <`VBMyExtensionTemplate>` с атрибутами, перечисленными в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d3d95-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="d3d95-134">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d3d95-134">Attribute</span></span>|<span data-ttu-id="d3d95-135">Описание</span><span class="sxs-lookup"><span data-stu-id="d3d95-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="d3d95-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d3d95-136">Required.</span></span> <span data-ttu-id="d3d95-137">Уникальный идентификатор расширения.</span><span class="sxs-lookup"><span data-stu-id="d3d95-137">A unique identifier for the extension.</span></span> <span data-ttu-id="d3d95-138">Если расширение с таким идентификатором уже добавлено в проект, пользователю не будет предложено добавить его повторно.</span><span class="sxs-lookup"><span data-stu-id="d3d95-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="d3d95-139">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d3d95-139">Required.</span></span> <span data-ttu-id="d3d95-140">Номер версии для шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="d3d95-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="d3d95-141">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d3d95-141">Optional.</span></span> <span data-ttu-id="d3d95-142">Имя сборки.</span><span class="sxs-lookup"><span data-stu-id="d3d95-142">An assembly name.</span></span> <span data-ttu-id="d3d95-143">Когда в проект добавляется ссылка на эту сборку, пользователю будет предложено добавить расширение `My` из этого шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="d3d95-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="d3d95-144">Добавление элемента \<CustomDataSignature> в VSTEMPLATE-файл</span><span class="sxs-lookup"><span data-stu-id="d3d95-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="d3d95-145">Чтобы указать, что шаблон элемента Visual Studio является расширением пространства имен `My`, необходимо изменить VSTEMPLATE-файл для этого шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="d3d95-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="d3d95-146">Добавьте элемент `<CustomDataSignature>` к элементу `<TemplateData>`.</span><span class="sxs-lookup"><span data-stu-id="d3d95-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="d3d95-147">Этот элемент `<CustomDataSignature>` должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d3d95-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="d3d95-148">Вы не можете изменять файлы непосредственно в сжатой папке (ZIP-файле).</span><span class="sxs-lookup"><span data-stu-id="d3d95-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="d3d95-149">Необходимо скопировать VSTEMPLATE-файл из сжатой папки, внести необходимые изменения, а затем заменить исходный VSTEMPLATE-файл в сжатой папке измененной копией.</span><span class="sxs-lookup"><span data-stu-id="d3d95-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="d3d95-150">В следующем примере показано содержимое VSTEMPLATE-файла после добавления элемента `<CustomDataSignature>`.</span><span class="sxs-lookup"><span data-stu-id="d3d95-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a><span data-ttu-id="d3d95-151">Установка шаблона</span><span class="sxs-lookup"><span data-stu-id="d3d95-151">Install the template</span></span>

<span data-ttu-id="d3d95-152">Чтобы установить шаблон, достаточно скопировать сжатую папку (*ZIP-файл*) в папку шаблонов элементов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3d95-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="d3d95-153">По умолчанию шаблоны элементов пользователя находятся в каталоге *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="d3d95-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="d3d95-154">Либо можно опубликовать шаблон в формате файла для Visual Studio Installer (*VSI-файла*).</span><span class="sxs-lookup"><span data-stu-id="d3d95-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3d95-155">См. также</span><span class="sxs-lookup"><span data-stu-id="d3d95-155">See also</span></span>

- [<span data-ttu-id="d3d95-156">Расширение пространства имен My в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3d95-156">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)
- [<span data-ttu-id="d3d95-157">Расширение модели приложения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3d95-157">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="d3d95-158">Настройка доступа к объектам через My</span><span class="sxs-lookup"><span data-stu-id="d3d95-158">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="d3d95-159">Страница "Мои расширения", конструктор проектов</span><span class="sxs-lookup"><span data-stu-id="d3d95-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
