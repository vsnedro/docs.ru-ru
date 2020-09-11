---
title: Обрезка автономных приложений
description: Сведения об обрезке автономных приложений для уменьшения их размера. .NET Core объединяет среду выполнения с автономно публикуемым приложением и обычно содержит больше компонентов среды выполнения, чем необходимо.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 9c2994c98a2ebe6f45b056256c2bda28db017fbf
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465485"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="c029a-104">Обрезка автономных развертываний и исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="c029a-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="c029a-105">[Модель развертывания с зависимостью от платформы](index.md#publish-framework-dependent) была наиболее успешной моделью развертывания с момента запуска .NET.</span><span class="sxs-lookup"><span data-stu-id="c029a-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="c029a-106">При таком сценарии разработчик приложения связывает только приложение и сторонние сборки, ожидая, что среда выполнения .NET и библиотеки платформы будут доступны на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="c029a-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="c029a-107">Эта модель развертывания продолжает доминировать и в .NET Core, но в некоторых случаях модель, зависящая от платформы, не является оптимальной.</span><span class="sxs-lookup"><span data-stu-id="c029a-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="c029a-108">Альтернативой является публикация [автономного приложения](index.md#publish-self-contained), в котором среда выполнения и платформа .NET Core объединены вместе с приложением и сборками сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="c029a-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="c029a-109">Автономная модель развертывания — это специализированная версия автономной модели развертывания, оптимизированная для уменьшения размера развертывания.</span><span class="sxs-lookup"><span data-stu-id="c029a-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="c029a-110">Минимизация размера развертывания является критически важным требованием для некоторых сценариев на стороне клиента, например приложений Blazor.</span><span class="sxs-lookup"><span data-stu-id="c029a-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="c029a-111">В зависимости от сложности приложения указывается только подмножество сборок платформы, а для запуска приложения требуется подмножество кода в каждой сборке.</span><span class="sxs-lookup"><span data-stu-id="c029a-111">Depending on the complexity of the application, only a subset of the framework assemblies are referenced, and a subset of the code within each assembly is required to run the application.</span></span> <span data-ttu-id="c029a-112">Неиспользуемые компоненты библиотеки не нужны, поэтому их можно удалить из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="c029a-112">The unused parts of the libraries are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="c029a-113">Однако существует риск того, что анализ времени сборки приложения может вызвать сбои во время выполнения из-за невозможности надежного анализа различных проблемных шаблонов кода (в основном сосредоточенных на использовании отражения).</span><span class="sxs-lookup"><span data-stu-id="c029a-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="c029a-114">Так как надежность не гарантируется, эта модель развертывания предлагается в качестве предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="c029a-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span>

<span data-ttu-id="c029a-115">Модуль анализа времени сборки предупреждает разработчиков шаблонов кода о проблемных шаблонах кода, чтобы можно было определить, какой другой код требуется.</span><span class="sxs-lookup"><span data-stu-id="c029a-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic to detect which other code is required.</span></span> <span data-ttu-id="c029a-116">Код можно снабдить атрибутами, чтобы указать, что еще следует включить в обрезку.</span><span class="sxs-lookup"><span data-stu-id="c029a-116">Code can be annotated with attributes to tell the trimmer what else to include.</span></span> <span data-ttu-id="c029a-117">Многие шаблоны отражения можно заменить на создание кода во время сборки с помощью [генераторов кода](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span><span class="sxs-lookup"><span data-stu-id="c029a-117">Many reflection patterns can be replaced with build-time code generation using [Source Generators](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span></span>

<span data-ttu-id="c029a-118">Режим обрезки для приложений настраивается с параметром `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="c029a-118">The trim mode for the applications is configured with the `TrimMode` setting.</span></span> <span data-ttu-id="c029a-119">Значение по умолчанию (`copyused`) объединяет сборки, на которые имеются ссылки, с приложением.</span><span class="sxs-lookup"><span data-stu-id="c029a-119">The default value is `copyused` and bundles referenced assemblies with the application.</span></span> <span data-ttu-id="c029a-120">Значение `link` используется с приложениями WebAssembly Blazor и обрезает неиспользуемый код в сборках.</span><span class="sxs-lookup"><span data-stu-id="c029a-120">The `link` value is used with Blazor WebAssembly applications and trims unused code within assemblies.</span></span> <span data-ttu-id="c029a-121">Предупреждения анализа обрезки предоставляют сведения о шаблонах кода, в которых невозможен полный анализ зависимостей.</span><span class="sxs-lookup"><span data-stu-id="c029a-121">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="c029a-122">Эти предупреждения подавляются по умолчанию и могут быть включены путем установки флага `SuppressTrimAnalysisWarnings` в значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c029a-122">These warnings are suppressed by default and can be turned on by setting the flag `SuppressTrimAnalysisWarnings` to `false`.</span></span> <span data-ttu-id="c029a-123">Дополнительные сведения о доступных параметрах обрезки см. в разделе [Параметры обрезки](trimming-options.md).</span><span class="sxs-lookup"><span data-stu-id="c029a-123">For more information about the trim options available, see [Trimming options](trimming-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c029a-124">Обрезка — это экспериментальная функция в .NET Core 3.1, 5.0, которая доступна _только_ для автономно публикуемых приложений.</span><span class="sxs-lookup"><span data-stu-id="c029a-124">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="c029a-125">Исключение сборок из процесса обрезки</span><span class="sxs-lookup"><span data-stu-id="c029a-125">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="c029a-126">В некоторых случаях функции обрезки не удается обнаружить ссылки.</span><span class="sxs-lookup"><span data-stu-id="c029a-126">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="c029a-127">Например, если в сборке среды выполнения отражение используется либо приложением, либо библиотекой, на которую ссылается приложение, прямые ссылки на эту сборку отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="c029a-127">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="c029a-128">Процессу обрезки неизвестно об этих косвенных ссылках, и он исключит библиотеку из папки опубликованных.</span><span class="sxs-lookup"><span data-stu-id="c029a-128">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="c029a-129">Когда код косвенно ссылается на сборку через отражение, можно исключить сборку из процесса обрезки с помощью параметра `<TrimmerRootAssembly>`.</span><span class="sxs-lookup"><span data-stu-id="c029a-129">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="c029a-130">В следующем примере показано исключение сборки с именем `System.Security` из процесса обрезки.</span><span class="sxs-lookup"><span data-stu-id="c029a-130">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="c029a-131">Обрезка приложения с помощью CLI</span><span class="sxs-lookup"><span data-stu-id="c029a-131">Trim your app - CLI</span></span>

<span data-ttu-id="c029a-132">Выполните обрезку приложения с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="c029a-132">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="c029a-133">При публикации приложения задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c029a-133">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="c029a-134">Опубликовать как автономное приложение для конкретной среды выполнения: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="c029a-134">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="c029a-135">Включить обрезку: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="c029a-135">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="c029a-136">В следующем примере показана публикация приложения для Windows в качестве автономного и обрезка выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c029a-136">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="c029a-137">В следующем примере приложение публикуется в режиме агрессивной обрезки, в котором неиспользованный код в сборках будет обрезан, а предупреждения об обрезке будут включены.</span><span class="sxs-lookup"><span data-stu-id="c029a-137">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="c029a-138">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="c029a-138">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="c029a-139">Обрезка приложения с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c029a-139">Trim your app - Visual Studio</span></span>

<span data-ttu-id="c029a-140">Visual Studio создает многократно используемые профили публикации, которые управляют процессом публикации приложения.</span><span class="sxs-lookup"><span data-stu-id="c029a-140">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="c029a-141">В **обозревателе решений** щелкните правой кнопкой мыши проект, который нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="c029a-141">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="c029a-142">Выберите команду **Опубликовать…** .</span><span class="sxs-lookup"><span data-stu-id="c029a-142">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Обозреватель решений с контекстным меню, где выделен пункт Опубликовать":::

    <span data-ttu-id="c029a-144">Если у вас еще нет профиля публикации, следуйте инструкциям по его созданию и выберите **Папка** в качестве типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="c029a-144">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="c029a-145">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c029a-145">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Профиль публикации Visual Studio с кнопкой Изменить":::

01. <span data-ttu-id="c029a-147">В диалоговом окне **Параметры профиля** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c029a-147">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="c029a-148">Параметру **Режим развертывания** задайте значение **Автономное**.</span><span class="sxs-lookup"><span data-stu-id="c029a-148">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="c029a-149">В качестве значения параметра **Целевая среда выполнения** укажите платформу, на которую будет выполнена публикация.</span><span class="sxs-lookup"><span data-stu-id="c029a-149">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="c029a-150">Выберите **Обрезать неиспользуемые сборки (в предварительной версии)** .</span><span class="sxs-lookup"><span data-stu-id="c029a-150">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="c029a-151">Нажмите кнопку **Сохранить**, чтобы сохранить параметры и вернуться в диалоговое окно **Публикация**.</span><span class="sxs-lookup"><span data-stu-id="c029a-151">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Диалоговое окно параметров профиля с выделенными параметрами для режима развертывания, целевой среды выполнения и обрезки неиспользуемых сборок.":::

01. <span data-ttu-id="c029a-153">Чтобы опубликовать обрезанное приложение, нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="c029a-153">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="c029a-154">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c029a-154">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="c029a-155">Обрезка приложения с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="c029a-155">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="c029a-156">В Visual Studio для Mac отсутствует возможность обрезки приложения во время публикации.</span><span class="sxs-lookup"><span data-stu-id="c029a-156">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="c029a-157">Вам потребуется вручную опубликовать приложение, выполнив инструкции в разделе [Образка приложения с помощью CLI](#trim-your-app---cli).</span><span class="sxs-lookup"><span data-stu-id="c029a-157">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="c029a-158">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="c029a-158">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c029a-159">См. также</span><span class="sxs-lookup"><span data-stu-id="c029a-159">See also</span></span>

- <span data-ttu-id="c029a-160">[Развертывание приложений .NET Core](index.md)</span><span class="sxs-lookup"><span data-stu-id="c029a-160">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="c029a-161">[Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="c029a-161">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="c029a-162">[Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="c029a-162">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="c029a-163">[Команда dotnet publish](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="c029a-163">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
