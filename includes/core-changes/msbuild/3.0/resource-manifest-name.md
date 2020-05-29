---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206208"
---
### <a name="resource-manifest-file-name-change"></a><span data-ttu-id="d28d0-101">Изменение имени файла манифеста для ресурса</span><span class="sxs-lookup"><span data-stu-id="d28d0-101">Resource manifest file name change</span></span>

<span data-ttu-id="d28d0-102">Начиная с .NET Core 3.0, в стандартных ситуациях MSBuild создает другие имена файлов манифеста для файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d28d0-102">Starting in .NET Core 3.0, in the default case, MSBuild generates a different manifest file name for resource files.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d28d0-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d28d0-103">Version introduced</span></span>

<span data-ttu-id="d28d0-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d28d0-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="d28d0-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="d28d0-105">Change description</span></span>

<span data-ttu-id="d28d0-106">До версии .NET Core 3.0, если для элемента `EmbeddedResource` в файле проекта не были указаны метаданные `LogicalName`, `ManifestResourceName`или `DependentUpon`, платформа MSBuild создавала имя файла манифеста в формате `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span><span class="sxs-lookup"><span data-stu-id="d28d0-106">Prior to .NET Core 3.0, if no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata was specified for an `EmbeddedResource` item in the project file, MSBuild generated a manifest file name in the pattern `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span></span> <span data-ttu-id="d28d0-107">Если в файле проекта не определено значение `RootNamespace`, по умолчанию используется имя проекта.</span><span class="sxs-lookup"><span data-stu-id="d28d0-107">If `RootNamespace` is not defined in the project file, it defaults to the project name.</span></span> <span data-ttu-id="d28d0-108">Например, для файла ресурсов с именем *Form1.resx* в корневом каталоге проекта создавался манифест с именем *MyProject.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="d28d0-108">For example, the generated manifest name for a resource file named *Form1.resx* in the root project directory was *MyProject.Form1.resources*.</span></span>

<span data-ttu-id="d28d0-109">Начиная с версии .NET Core 3.0, при размещении файла ресурса в одной папке с одноименным исходным файлом, (*Form1.resx* и *Form1.cs*), MSBuild использует сведения о типе из исходного файла для создания имени файла манифеста в формате `<Namespace>.<ClassName>.resources`.</span><span class="sxs-lookup"><span data-stu-id="d28d0-109">Starting in .NET Core 3.0, if a resource file is colocated with a source file of the same name (for example, *Form1.resx* and *Form1.cs*), MSBuild uses type information from the source file to generate the manifest file name in the pattern `<Namespace>.<ClassName>.resources`.</span></span> <span data-ttu-id="d28d0-110">Пространство имен и имя класса извлекаются из первого типа в исходном файле, найденном в той же папке.</span><span class="sxs-lookup"><span data-stu-id="d28d0-110">The namespace and class name are extracted from the first type in the colocated source file.</span></span> <span data-ttu-id="d28d0-111">Например, для файла ресурсов с именем *Form1.resx*, который расположен в одной папке с исходным файлом *Form1.cs*, создается манифест с именем *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="d28d0-111">For example, the generated manifest name for a resource file named *Form1.resx* that's colocated with a source file named *Form1.cs* is *MyNamespace.Form1.resources*.</span></span> <span data-ttu-id="d28d0-112">Важно отметить, что первая часть имени файла отличается от имени в прежних версиях .NET Core (*MyNamespace* вместо *MyProject*).</span><span class="sxs-lookup"><span data-stu-id="d28d0-112">The key thing to note is that the first part of the file name is different to prior versions of .NET Core (*MyNamespace* instead of *MyProject*).</span></span>

> [!NOTE]
> <span data-ttu-id="d28d0-113">Если для элемента `EmbeddedResource` в файле проекта указаны метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, это изменение не применяется к соответствующему файлу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d28d0-113">If you have `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata specified on an `EmbeddedResource` item in the project file, then this change does not affect that resource file.</span></span>

<span data-ttu-id="d28d0-114">Это критическое изменение было введено одновременно с добавлением свойства `EmbeddedResourceUseDependentUponConvention` для проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d28d0-114">This breaking change was introduced with the addition of the `EmbeddedResourceUseDependentUponConvention` property to .NET Core projects.</span></span> <span data-ttu-id="d28d0-115">По умолчанию файлы ресурсов не указаны явным образом в файле проекта .NET Core, поэтому в них нет метаданных `DependentUpon`, которые позволяют задать формат именования созданного файла *.resources*.</span><span class="sxs-lookup"><span data-stu-id="d28d0-115">By default, resource files aren't explicitly listed in a .NET Core project file, so they have no `DependentUpon` metadata to specify how to name the generated *.resources* file.</span></span> <span data-ttu-id="d28d0-116">Если `EmbeddedResourceUseDependentUponConvention` имеет значение `true` (используется по умолчанию), MSBuild ищет в той же папке исходный файл и извлекает из этого файла пространство имен и имя класса.</span><span class="sxs-lookup"><span data-stu-id="d28d0-116">When `EmbeddedResourceUseDependentUponConvention` is set to `true`, which is the default, MSBuild looks for a colocated source file and extracts a namespace and class name from that file.</span></span> <span data-ttu-id="d28d0-117">Если для `EmbeddedResourceUseDependentUponConvention` задано значение `false`, MSBuild создает имя манифеста по правилам для прежних версий, то есть объединяет `RootNamespace` и относительный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="d28d0-117">If you set `EmbeddedResourceUseDependentUponConvention` to `false`, MSBuild generates the manifest name according to the previous behavior, which combines `RootNamespace` and the relative file path.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d28d0-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="d28d0-118">Recommended action</span></span>

<span data-ttu-id="d28d0-119">В большинстве случаев разработчикам не нужно предпринимать по этому поводу никаких действий, и приложение должно работать нормально.</span><span class="sxs-lookup"><span data-stu-id="d28d0-119">In most cases, no action is required on the part of the developer, and your app should continue to work.</span></span> <span data-ttu-id="d28d0-120">Если же это изменение нарушит работу приложения, вы можете выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d28d0-120">However, if this change breaks your app, you can either:</span></span>

- <span data-ttu-id="d28d0-121">Измените код так, чтобы он ожидал новое имя манифеста.</span><span class="sxs-lookup"><span data-stu-id="d28d0-121">Change your code to expect the new manifest name.</span></span>

- <span data-ttu-id="d28d0-122">Откажитесь от нового соглашения об именовании, указав в файле проекта параметр `EmbeddedResourceUseDependentUponConvention` со значением `false`.</span><span class="sxs-lookup"><span data-stu-id="d28d0-122">Opt out of the new naming convention by setting `EmbeddedResourceUseDependentUponConvention` to `false` in your project file.</span></span>

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="d28d0-123">Категория</span><span class="sxs-lookup"><span data-stu-id="d28d0-123">Category</span></span>

<span data-ttu-id="d28d0-124">MSBuild</span><span class="sxs-lookup"><span data-stu-id="d28d0-124">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d28d0-125">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d28d0-125">Affected APIs</span></span>

<span data-ttu-id="d28d0-126">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d28d0-126">N/A</span></span>
