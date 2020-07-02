---
title: Ресурсы приложения, содержимое и файлы данных
description: Ознакомьтесь с специальной поддержкой по настройке, идентификации и использованию файлов данных приложения в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: 324b3eb922f0fd1d1d9ad00105a06a7fbdb8effd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622865"
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="a91a2-103">Ресурсы, Содержимое и Файлы данных WPF-приложения</span><span class="sxs-lookup"><span data-stu-id="a91a2-103">WPF Application Resource, Content, and Data Files</span></span>
<span data-ttu-id="a91a2-104">Приложения Microsoft Windows часто зависят от файлов, содержащих неисполняемые данные, такие как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , изображения, видео и звук.</span><span class="sxs-lookup"><span data-stu-id="a91a2-104">Microsoft Windows applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="a91a2-105">Windows Presentation Foundation (WPF) предлагает специальную поддержку для настройки, идентификации и использования этих типов файлов данных, которые называются файлами данных приложения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-105">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="a91a2-106">Эта поддержка относится к определенному набору типов файлов данных приложения, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="a91a2-106">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="a91a2-107">**Файлы ресурсов**. файлы данных, компилируемые в исполняемый файл или СБОРКУ библиотеки WPF.</span><span class="sxs-lookup"><span data-stu-id="a91a2-107">**Resource Files**: Data files that are compiled into either an executable or library WPF assembly.</span></span>  
  
- <span data-ttu-id="a91a2-108">**Файлы содержимого**: автономные файлы данных с явной связью с исполняемой сборкой WPF.</span><span class="sxs-lookup"><span data-stu-id="a91a2-108">**Content Files**: Standalone data files that have an explicit association with an executable WPF assembly.</span></span>  
  
- <span data-ttu-id="a91a2-109">**Файлы исходного узла**: автономные файлы данных, не имеющие связи с исполняемой сборкой WPF.</span><span class="sxs-lookup"><span data-stu-id="a91a2-109">**Site of Origin Files**: Standalone data files that have no association with an executable WPF assembly.</span></span>  
  
 <span data-ttu-id="a91a2-110">Важным отличием между этими тремя типами файлов является то, что файлы ресурсов и файлы содержимого известны во время построения. Сборка содержит информацию о них.</span><span class="sxs-lookup"><span data-stu-id="a91a2-110">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="a91a2-111">Однако для файлов исходного узла сборка может вообще не иметь сведений о них или неявного набора знаний через универсальный код ресурса (URI) типа pack. в последнем случае нет никакой гарантии, что файл исходного узла, на который указывает ссылка, фактически существует.</span><span class="sxs-lookup"><span data-stu-id="a91a2-111">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="a91a2-112">Для ссылки на файлы данных приложения Windows Presentation Foundation (WPF) использует схему универсального идентификатора ресурса (URI) типа Pack, которая подробно описана в разделе URI типа " [Pack" в WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="a91a2-112">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="a91a2-113">В этом разделе описывается настройка и использование файлов данных приложения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-113">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>
## <a name="resource-files"></a><span data-ttu-id="a91a2-114">Файлы ресурсов</span><span class="sxs-lookup"><span data-stu-id="a91a2-114">Resource Files</span></span>  
 <span data-ttu-id="a91a2-115">Если файл данных приложения всегда должен быть доступен для приложения, то единственный способ гарантировать доступность — скомпилировать его в главную исполняемую сборку приложения или в одну из его указанных ссылками сборок.</span><span class="sxs-lookup"><span data-stu-id="a91a2-115">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="a91a2-116">Этот тип файла данных приложения называется *файлом ресурсов*.</span><span class="sxs-lookup"><span data-stu-id="a91a2-116">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="a91a2-117">Нужно использовать файлы ресурсов, если:</span><span class="sxs-lookup"><span data-stu-id="a91a2-117">You should use resource files when:</span></span>  
  
- <span data-ttu-id="a91a2-118">Не нужно обновлять содержимое файла ресурсов после его компиляции в сборку.</span><span class="sxs-lookup"><span data-stu-id="a91a2-118">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="a91a2-119">Необходимо упростить распространение приложения за счет уменьшения количества зависимостей между файлами.</span><span class="sxs-lookup"><span data-stu-id="a91a2-119">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="a91a2-120">Файл данных приложения должен быть локализуемой (см. [Общие сведения о глобализации и локализации WPF](../advanced/wpf-globalization-and-localization-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="a91a2-120">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a91a2-121">Файлы ресурсов, описанные в этом разделе, отличаются от файлов ресурсов, описанных в [ресурсах XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) , и отличаются от внедренных или связанных ресурсов, описанных в статье [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a91a2-121">The resource files described in this section are different than the resource files described in [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="a91a2-122">Настройка файлов ресурсов</span><span class="sxs-lookup"><span data-stu-id="a91a2-122">Configuring Resource Files</span></span>  
 <span data-ttu-id="a91a2-123">В WPF файл ресурсов — это файл, включенный в проект Microsoft Build Engine (MSBuild) в качестве `Resource` элемента.</span><span class="sxs-lookup"><span data-stu-id="a91a2-123">In WPF, a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="a91a2-124">В Visual Studio создайте файл ресурсов, добавив файл в проект и задав для него значение `Build Action` `Resource` .</span><span class="sxs-lookup"><span data-stu-id="a91a2-124">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="a91a2-125">При построении проекта MSBuild компилирует ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="a91a2-125">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="a91a2-126">Использование файлов ресурсов</span><span class="sxs-lookup"><span data-stu-id="a91a2-126">Using Resource Files</span></span>  
 <span data-ttu-id="a91a2-127">Чтобы загрузить файл ресурсов, можно вызвать <xref:System.Windows.Application.GetResourceStream%2A> метод <xref:System.Windows.Application> класса, передав URI типа Pack, который идентифицирует нужный файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a91a2-127">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="a91a2-128"><xref:System.Windows.Application.GetResourceStream%2A>Возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл ресурсов как <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="a91a2-128"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="a91a2-129">Например, в следующем коде показано, как использовать <xref:System.Windows.Application.GetResourceStream%2A> для загрузки <xref:System.Windows.Controls.Page> файла ресурсов и его установки в качестве содержимого объекта <xref:System.Windows.Controls.Frame> ( `pageFrame` ):</span><span class="sxs-lookup"><span data-stu-id="a91a2-129">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="a91a2-130">Хотя при вызове <xref:System.Windows.Application.GetResourceStream%2A> предоставляется доступ к <xref:System.IO.Stream> , необходимо выполнить дополнительную работу по преобразованию в тип свойства, для которого будет задано значение.</span><span class="sxs-lookup"><span data-stu-id="a91a2-130">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="a91a2-131">Вместо этого можно позволить WPF относиться к открытию и преобразованию, <xref:System.IO.Stream> загружая файл ресурсов непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a91a2-131">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="a91a2-132">В следующем примере показано, как загрузить объект <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> ( `pageFrame` ) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a91a2-132">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="a91a2-133">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="a91a2-133">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="a91a2-134">Файлы кода приложения как файлы ресурсов</span><span class="sxs-lookup"><span data-stu-id="a91a2-134">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="a91a2-135">На Специальный набор файлов кода приложения WPF можно ссылаться с помощью URI типа "Pack", включая окна, страницы, документы нефиксированного формата и словари ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a91a2-135">A special set of WPF application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="a91a2-136">Например, можно задать <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> свойство с URI типа Pack, который ссылается на окно или страницу, которые необходимо загрузить при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-136">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="a91a2-137">Это можно сделать, когда XAML-файл включается в проект MSBuild как `Page` элемент.</span><span class="sxs-lookup"><span data-stu-id="a91a2-137">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="a91a2-138">В Visual Studio вы добавите в проект новый,,, <xref:System.Windows.Window> <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.FlowDocument> или <xref:System.Windows.ResourceDictionary> , `Build Action` для файла разметки по умолчанию будет выбрано значение `Page` .</span><span class="sxs-lookup"><span data-stu-id="a91a2-138">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="a91a2-139">При компиляции проекта с `Page` элементами [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы преобразуются в двоичный формат и компилируются в связанную сборку.</span><span class="sxs-lookup"><span data-stu-id="a91a2-139">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="a91a2-140">Следовательно, эти файлы можно использовать таким же образом, как и обычные файлы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a91a2-140">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a91a2-141">Если [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл настроен в качестве `Resource` элемента и не имеет файла кода программной части, то необработанный код [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] компилируется в сборку, а не в двоичную версию RAW [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a91a2-141">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>
## <a name="content-files"></a><span data-ttu-id="a91a2-142">Файлы с содержимым</span><span class="sxs-lookup"><span data-stu-id="a91a2-142">Content Files</span></span>  
 <span data-ttu-id="a91a2-143">*Файл содержимого* распространяется в виде свободного файла вместе с исполняемой сборкой.</span><span class="sxs-lookup"><span data-stu-id="a91a2-143">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="a91a2-144">Несмотря на то, что они не компилируются в сборку, сборки компилируются с метаданными, которые устанавливают связь с каждым файлом содержимого.</span><span class="sxs-lookup"><span data-stu-id="a91a2-144">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="a91a2-145">Файлы содержимого необходимо использовать, если приложению требуется определенный набор файлов данных приложения, которые нужно обновлять без повторной компиляции использующей их сборки.</span><span class="sxs-lookup"><span data-stu-id="a91a2-145">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="a91a2-146">Настройка файлов содержимого</span><span class="sxs-lookup"><span data-stu-id="a91a2-146">Configuring Content Files</span></span>  
 <span data-ttu-id="a91a2-147">Чтобы добавить файл содержимого в проект, в качестве элемента необходимо включить файл данных приложения `Content` .</span><span class="sxs-lookup"><span data-stu-id="a91a2-147">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="a91a2-148">Более того, поскольку файл содержимого не компилируется непосредственно в сборку, необходимо задать `CopyToOutputDirectory` элемент метаданных MSBuild, чтобы указать, что файл содержимого копируется в расположение, относящееся к построенной сборке.</span><span class="sxs-lookup"><span data-stu-id="a91a2-148">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="a91a2-149">Если требуется, чтобы ресурс копировался в выходную папку сборки при каждом построении проекта, необходимо задать для `CopyToOutputDirectory` элемента метаданных `Always` значение.</span><span class="sxs-lookup"><span data-stu-id="a91a2-149">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="a91a2-150">В противном случае можно гарантировать, что только последняя версия ресурса копируется в выходную папку сборки с использованием `PreserveNewest` значения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-150">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="a91a2-151">Ниже показан файл, настроенный как файл содержимого, который копируется в папку выходных данных построения только при добавлении новой версии ресурса в проект.</span><span class="sxs-lookup"><span data-stu-id="a91a2-151">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="a91a2-152">В Visual Studio вы создаете файл содержимого, добавляя файл в проект и присвоив ему значение `Build Action` , а также установите для него значение `Content` `Copy to Output Directory` `Copy always` (то же, что `Always` `Copy if newer` `PreserveNewest` и).</span><span class="sxs-lookup"><span data-stu-id="a91a2-152">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="a91a2-153">При построении проекта <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> атрибут компилируется в метаданные сборки для каждого файла содержимого.</span><span class="sxs-lookup"><span data-stu-id="a91a2-153">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="a91a2-154">Значение параметра <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> указывает путь к файлу содержимого относительно его положения в проекте.</span><span class="sxs-lookup"><span data-stu-id="a91a2-154">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="a91a2-155">Например, если файл содержимого находился во вложенной папке проекта, то в это значение будет включен дополнительный путь к данным <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> .</span><span class="sxs-lookup"><span data-stu-id="a91a2-155">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="a91a2-156"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>Значение является также значением пути к файлу содержимого в выходной папке построения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-156">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="a91a2-157">Использование файлов содержимого</span><span class="sxs-lookup"><span data-stu-id="a91a2-157">Using Content Files</span></span>  
 <span data-ttu-id="a91a2-158">Чтобы загрузить файл содержимого, можно вызвать <xref:System.Windows.Application.GetContentStream%2A> метод <xref:System.Windows.Application> класса, передав URI типа Pack, который идентифицирует нужный файл содержимого.</span><span class="sxs-lookup"><span data-stu-id="a91a2-158">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="a91a2-159"><xref:System.Windows.Application.GetContentStream%2A>Возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл содержимого в виде <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="a91a2-159"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="a91a2-160">Например, в следующем коде показано, как использовать <xref:System.Windows.Application.GetContentStream%2A> для загрузки <xref:System.Windows.Controls.Page> файла содержимого и его установки в качестве содержимого объекта <xref:System.Windows.Controls.Frame> ( `pageFrame` ).</span><span class="sxs-lookup"><span data-stu-id="a91a2-160">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="a91a2-161">Хотя при вызове <xref:System.Windows.Application.GetContentStream%2A> предоставляется доступ к <xref:System.IO.Stream> , необходимо выполнить дополнительную работу по преобразованию в тип свойства, для которого будет задано значение.</span><span class="sxs-lookup"><span data-stu-id="a91a2-161">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="a91a2-162">Вместо этого можно позволить WPF относиться к открытию и преобразованию, <xref:System.IO.Stream> загружая файл ресурсов непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a91a2-162">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="a91a2-163">В следующем примере показано, как загрузить объект <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> ( `pageFrame` ) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a91a2-163">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="a91a2-164">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="a91a2-164">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a><span data-ttu-id="a91a2-165">Файлы исходного узла</span><span class="sxs-lookup"><span data-stu-id="a91a2-165">Site of Origin Files</span></span>  
 <span data-ttu-id="a91a2-166">Файлы ресурсов имеют явную связь со сборками, которые они распределяют вместе, как определено в <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> .</span><span class="sxs-lookup"><span data-stu-id="a91a2-166">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="a91a2-167">Но иногда необходимо установить неявную либо несуществующую связь между сборкой и файлом данных приложения, например, в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="a91a2-167">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="a91a2-168">Файл не существует во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="a91a2-168">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="a91a2-169">Неизвестно, какие файлы потребуются для сборки до времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-169">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="a91a2-170">Нужна возможность обновлять файлы без повторной компиляции сборки, связанной с ними.</span><span class="sxs-lookup"><span data-stu-id="a91a2-170">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="a91a2-171">Приложение использует большие файлы данных, такие как аудио и видео, и необходимо, чтобы пользователи могли их загружать только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a91a2-171">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="a91a2-172">Эти типы файлов можно загрузить с помощью традиционных схем URI, таких как `file:///` `http://` схемы и.</span><span class="sxs-lookup"><span data-stu-id="a91a2-172">It is possible to load these types of files by using traditional URI schemes, such as the `file:///` and `http://` schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="a91a2-173">Однако `file:///` `http://` для схем и требуется, чтобы приложение имело полное доверие.</span><span class="sxs-lookup"><span data-stu-id="a91a2-173">However, the `file:///` and `http://` schemes require your application to have full trust.</span></span> <span data-ttu-id="a91a2-174">Если приложение является приложением браузера XAML (XBAP), которое было запущено из Интернета или интрасети, и запрашивает только набор разрешений, разрешенных для приложений, запускаемых из этих расположений, свободные файлы могут загружаться только из исходного узла приложения (расположение запуска).</span><span class="sxs-lookup"><span data-stu-id="a91a2-174">If your application is a XAML browser application (XBAP) that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="a91a2-175">Такие файлы называются файлами *исходного узла* .</span><span class="sxs-lookup"><span data-stu-id="a91a2-175">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="a91a2-176">Файлы исходного узла являются единственным вариантом для приложений с частичным доверием, хотя и не ограничиваются такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="a91a2-176">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="a91a2-177">Приложениям с полным доверием, возможно, все равно придется загружать файлы данных приложений, о которых они не знают во время построения. Хотя приложения с полным доверием могут использовать схему file:///, вероятнее всего, файлы данных приложения будут установлены в одну папку или вложенную папку со сборкой приложения.</span><span class="sxs-lookup"><span data-stu-id="a91a2-177">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="a91a2-178">В этом случае использовать ссылки на исходный узел проще, чем использовать file:///, так как последнее требует разработки полного пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="a91a2-178">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a91a2-179">Файлы исходного узла не кэшируются с помощью приложения браузера XAML (XBAP) на клиентском компьютере, а файлы содержимого —.</span><span class="sxs-lookup"><span data-stu-id="a91a2-179">Site of origin files are not cached with an XAML browser application (XBAP) on a client machine, while content files are.</span></span> <span data-ttu-id="a91a2-180">Следовательно, они загружаются только по специальному запросу.</span><span class="sxs-lookup"><span data-stu-id="a91a2-180">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="a91a2-181">Если приложение браузера XAML (XBAP) имеет большие файлы мультимедиа, их настройка в качестве файлов исходного узла означает, что начальный запуск приложения выполняется гораздо быстрее, а файлы загружаются по требованию.</span><span class="sxs-lookup"><span data-stu-id="a91a2-181">If an XAML browser application (XBAP) application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="a91a2-182">Настройка файлов исходного узла</span><span class="sxs-lookup"><span data-stu-id="a91a2-182">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="a91a2-183">Если файлы исходного сайта не существуют или неизвестны во время компиляции, необходимо использовать традиционные механизмы развертывания для обеспечения доступности необходимых файлов во время выполнения, в том числе с помощью `XCopy` программы командной строки или Microsoft установщик Windows.</span><span class="sxs-lookup"><span data-stu-id="a91a2-183">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the Microsoft Windows Installer.</span></span>  
  
 <span data-ttu-id="a91a2-184">Если во время компиляции вы узнаете, какие файлы необходимо найти на исходном узле, но все равно хотите избежать явной зависимости, можно добавить эти файлы в проект MSBuild как `None` элемент.</span><span class="sxs-lookup"><span data-stu-id="a91a2-184">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="a91a2-185">Как и в случае с файлами содержимого, необходимо задать `CopyToOutputDirectory` атрибут MSBuild, чтобы указать, что файл исходного узла копируется в расположение относительно сборки, указав либо значение, либо `Always` `PreserveNewest` значение.</span><span class="sxs-lookup"><span data-stu-id="a91a2-185">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="a91a2-186">В Visual Studio создайте файл исходного узла, добавив файл в проект и задав для него значение `Build Action` `None` .</span><span class="sxs-lookup"><span data-stu-id="a91a2-186">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="a91a2-187">При построении проекта MSBuild копирует указанные файлы в выходную папку сборки.</span><span class="sxs-lookup"><span data-stu-id="a91a2-187">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="a91a2-188">Использование файлов исходного узла</span><span class="sxs-lookup"><span data-stu-id="a91a2-188">Using Site of Origin Files</span></span>  
 <span data-ttu-id="a91a2-189">Чтобы загрузить файл исходного узла, можно вызвать <xref:System.Windows.Application.GetRemoteStream%2A> метод <xref:System.Windows.Application> класса, передав URI типа Pack, который идентифицирует нужный файл исходного узла.</span><span class="sxs-lookup"><span data-stu-id="a91a2-189">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="a91a2-190"><xref:System.Windows.Application.GetRemoteStream%2A>Возвращает <xref:System.Windows.Resources.StreamResourceInfo> объект, который предоставляет файл исходного узла как <xref:System.IO.Stream> и описывает его тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="a91a2-190"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="a91a2-191">В следующем примере кода показано, как использовать <xref:System.Windows.Application.GetRemoteStream%2A> для загрузки <xref:System.Windows.Controls.Page> файла исходного узла и задать его в качестве содержимого объекта <xref:System.Windows.Controls.Frame> ( `pageFrame` ).</span><span class="sxs-lookup"><span data-stu-id="a91a2-191">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="a91a2-192">Хотя при вызове <xref:System.Windows.Application.GetRemoteStream%2A> предоставляется доступ к <xref:System.IO.Stream> , необходимо выполнить дополнительную работу по преобразованию в тип свойства, для которого будет задано значение.</span><span class="sxs-lookup"><span data-stu-id="a91a2-192">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="a91a2-193">Вместо этого можно позволить WPF относиться к открытию и преобразованию, <xref:System.IO.Stream> загружая файл ресурсов непосредственно в свойство типа с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a91a2-193">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="a91a2-194">В следующем примере показано, как загрузить объект <xref:System.Windows.Controls.Page> непосредственно в <xref:System.Windows.Controls.Frame> ( `pageFrame` ) с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a91a2-194">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="a91a2-195">В следующем примере показан эквивалент разметки предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="a91a2-195">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="a91a2-196">Повторное построение после изменения типа построения</span><span class="sxs-lookup"><span data-stu-id="a91a2-196">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="a91a2-197">После изменения типа построения файла данных приложения необходимо перестроить все приложение, чтобы обеспечить применение этих изменений.</span><span class="sxs-lookup"><span data-stu-id="a91a2-197">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="a91a2-198">Если просто выполнить построение приложения, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="a91a2-198">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a91a2-199">См. также</span><span class="sxs-lookup"><span data-stu-id="a91a2-199">See also</span></span>

- [<span data-ttu-id="a91a2-200">URI типа "pack" в WPF</span><span class="sxs-lookup"><span data-stu-id="a91a2-200">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
