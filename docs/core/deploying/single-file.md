---
title: Приложение с одним файлом
description: Узнайте, что такое приложение с одним файлом и зачем нужно использовать эту модель развертывания приложения.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495757"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="aa255-103">Развертывание и выполнение в виде отдельного файла</span><span class="sxs-lookup"><span data-stu-id="aa255-103">Single file deployment and executable</span></span>

<span data-ttu-id="aa255-104">Объединение всех зависящих от приложения файлов в один двоичный файл предоставляет разработчику приложения привлекательный вариант развертывания и распространения приложения в виде одного файла.</span><span class="sxs-lookup"><span data-stu-id="aa255-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="aa255-105">Эта модель развертывания была доступна с момента выпуска .NET Core 3.0 и улучшена в .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="aa255-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="aa255-106">Ранее в .NET Core 3.0, когда пользователь запускал приложение с одним файлом, узел .NET Core перед запуском приложения сначала извлекал все файлы во временный каталог.</span><span class="sxs-lookup"><span data-stu-id="aa255-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="aa255-107">В .NET 5.0 этот подход был улучшен, позволяя запускать код напрямую без необходимости извлекать файлы из приложения.</span><span class="sxs-lookup"><span data-stu-id="aa255-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="aa255-108">Развертывание в одном файле доступно как для [зависимой от платформы модели развертывания](index.md#publish-framework-dependent), так и для [автономных приложений](index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="aa255-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="aa255-109">Размер одного файла для автономного приложения будет большим, так как он будет включать в себя среду выполнения и библиотеки платформы.</span><span class="sxs-lookup"><span data-stu-id="aa255-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="aa255-110">Вариант развертывания в виде одного файла можно сочетать с параметрами публикации [ReadyToRun](../tools/dotnet-publish.md) и [Обрезка (экспериментальная функция в .NET 5.0)](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

<span data-ttu-id="aa255-111">Существуют некоторые предостережения, которые необходимо учитывать при использовании одного файла. Первое из них — это использование сведений о пути для поиска файла относительно расположения приложения.</span><span class="sxs-lookup"><span data-stu-id="aa255-111">There are some caveats that you need to be aware for single-file use, first of which is the use of path information to locate a file relative to the location of your application.</span></span> <span data-ttu-id="aa255-112">API <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> будет возвращать пустую строку, что является поведением по умолчанию для сборок, загруженных из памяти.</span><span class="sxs-lookup"><span data-stu-id="aa255-112">The <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API will return an empty string, which is the default behavior for assemblies loaded from memory.</span></span> <span data-ttu-id="aa255-113">Во время сборки компилятор выдаст предупреждение для этого API, чтобы предупредить разработчика о специфичном поведении.</span><span class="sxs-lookup"><span data-stu-id="aa255-113">The compiler will give a warning for this API during build time to alert the developer to the specific behavior.</span></span> <span data-ttu-id="aa255-114">Если требуется получить путь к каталогу приложения, то API <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> возвращает каталог, в котором находится AppHost (сам пакет в одном файлом).</span><span class="sxs-lookup"><span data-stu-id="aa255-114">If the path to the application directory is needed, the <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API will return the directory where the AppHost (the single-file bundle itself) resides.</span></span> <span data-ttu-id="aa255-115">Управляемые приложения C++ плохо подходят для развертывания в одном файле, поэтому рекомендуется писать приложения на C#, если требуется совместимость с развертыванием в одном файле.</span><span class="sxs-lookup"><span data-stu-id="aa255-115">Managed C++ applications aren't well suited for single-file deployment and we recommend that you write applications in C# to be single-file compatible.</span></span>

<span data-ttu-id="aa255-116">По умолчанию один файл не включает собственные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="aa255-116">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="aa255-117">В Linux предварительно связывается среда выполнения с пакетом, а в каталоге, в котором размещается приложение с одним файлом, развертываются только собственные библиотеки приложения.</span><span class="sxs-lookup"><span data-stu-id="aa255-117">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="aa255-118">В Windows предварительно связывается только код размещения, а в каталоге, в котором размещается приложение с одним файлом, развертываются как библиотеки среды выполнения, так и собственные библиотеки приложения.</span><span class="sxs-lookup"><span data-stu-id="aa255-118">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="aa255-119">Это позволяет обеспечить эффективную отладку, для которой требуется, чтобы собственные файлы были исключены из одного файла.</span><span class="sxs-lookup"><span data-stu-id="aa255-119">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="aa255-120">Можно задать флаг `IncludeNativeLibrariesForSelfExtract`, чтобы включить собственные библиотеки в один пакет, но эти файлы будут извлечены во временный каталог на клиентском компьютере при запуске приложения с одним файлом.</span><span class="sxs-lookup"><span data-stu-id="aa255-120">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="aa255-121">Исключить файлы из внедрения</span><span class="sxs-lookup"><span data-stu-id="aa255-121">Exclude files from being embedded</span></span>

<span data-ttu-id="aa255-122">Некоторые файлы можно явно исключить из внедрения в один файл, установив следующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="aa255-122">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="aa255-123">Например, чтобы поместить некоторые файлы в каталог публикации, но не объединять их в один файл, укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="aa255-123">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="aa255-124">Публикация приложения с одним файлом с помощью CLI</span><span class="sxs-lookup"><span data-stu-id="aa255-124">Publish a single file app - CLI</span></span>

<span data-ttu-id="aa255-125">Опубликуйте приложение с одним файлом с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-125">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="aa255-126">При публикации приложения задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="aa255-126">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="aa255-127">Опубликовать для конкретной среды выполнения: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="aa255-127">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="aa255-128">Опубликовать в виде одного файла: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="aa255-128">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="aa255-129">В следующем примере приложение для Windows публикуется как автономное приложение с одним файлом.</span><span class="sxs-lookup"><span data-stu-id="aa255-129">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="aa255-130">В следующем примере приложение для Linux публикуется как зависимое от платформы приложение с одним файлом.</span><span class="sxs-lookup"><span data-stu-id="aa255-130">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="aa255-131">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-131">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="aa255-132">Публикация приложения с одним файлом с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa255-132">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="aa255-133">Visual Studio создает многократно используемые профили публикации, которые управляют процессом публикации приложения.</span><span class="sxs-lookup"><span data-stu-id="aa255-133">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="aa255-134">В **обозревателе решений** щелкните правой кнопкой мыши проект, который нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="aa255-134">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="aa255-135">Нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="aa255-135">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Обозреватель решений с контекстным меню, где выделен пункт Опубликовать":::

    <span data-ttu-id="aa255-137">Если у вас еще нет профиля публикации, следуйте инструкциям по его созданию и выберите **Папка** в качестве типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="aa255-137">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="aa255-138">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="aa255-138">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Профиль публикации Visual Studio с кнопкой Изменить":::

01. <span data-ttu-id="aa255-140">В диалоговом окне **Параметры профиля** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="aa255-140">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="aa255-141">Параметру **Режим развертывания** задайте значение **Автономное**.</span><span class="sxs-lookup"><span data-stu-id="aa255-141">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="aa255-142">В качестве значения параметра **Целевая среда выполнения** укажите платформу, на которую будет выполнена публикация.</span><span class="sxs-lookup"><span data-stu-id="aa255-142">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="aa255-143">Выберите **Создать отдельный файл**.</span><span class="sxs-lookup"><span data-stu-id="aa255-143">Select **Produce single file**.</span></span>

    <span data-ttu-id="aa255-144">Нажмите кнопку **Сохранить**, чтобы сохранить параметры и вернуться в диалоговое окно **Публикация**.</span><span class="sxs-lookup"><span data-stu-id="aa255-144">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Диалоговое окно параметров профиля с выделенными параметрами для режима развертывания, целевой среды выполнения и создания отдельного файла":::

01. <span data-ttu-id="aa255-146">Чтобы опубликовать приложение с одним файлом, нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="aa255-146">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="aa255-147">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-147">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="aa255-148">Публикация приложения с одним файлом с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="aa255-148">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="aa255-149">В Visual Studio для Mac отсутствует возможность публикации приложения в виде одного файла.</span><span class="sxs-lookup"><span data-stu-id="aa255-149">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="aa255-150">Вам потребуется опубликовать приложение вручную, выполнив инструкции из раздела [Публикация приложения с одним файлом с помощью CLI](#publish-a-single-file-app---cli).</span><span class="sxs-lookup"><span data-stu-id="aa255-150">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="aa255-151">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-151">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa255-152">См. также</span><span class="sxs-lookup"><span data-stu-id="aa255-152">See also</span></span>

- <span data-ttu-id="aa255-153">[Развертывание приложений .NET Core](index.md)</span><span class="sxs-lookup"><span data-stu-id="aa255-153">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="aa255-154">[Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="aa255-154">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="aa255-155">[Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="aa255-155">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="aa255-156">[Команда `dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-156">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
