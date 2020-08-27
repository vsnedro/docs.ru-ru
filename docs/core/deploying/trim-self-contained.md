---
title: Обрезка автономных приложений
description: Сведения об обрезке автономных приложений для уменьшения их размера. .NET Core объединяет среду выполнения с автономно публикуемым приложением и обычно содержит больше компонентов среды выполнения, чем необходимо.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 0fde409e9e5911213855ab206368d302b73eebb3
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720128"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="21e29-104">Обрезка автономных развертываний и исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="21e29-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="21e29-105">[Модель развертывания с зависимостью от платформы](index.md#publish-framework-dependent) была наиболее успешной моделью развертывания с момента запуска .NET.</span><span class="sxs-lookup"><span data-stu-id="21e29-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="21e29-106">При таком сценарии разработчик приложения связывает только приложение и сторонние сборки, ожидая, что среда выполнения .NET и библиотеки платформы будут доступны на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="21e29-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="21e29-107">Эта модель развертывания продолжает доминировать и в .NET Core, но в некоторых случаях модель, зависящая от платформы, не является оптимальной.</span><span class="sxs-lookup"><span data-stu-id="21e29-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="21e29-108">Альтернативой является публикация [автономного приложения](index.md#publish-self-contained), в котором среда выполнения и платформа .NET Core объединены вместе с приложением и сборками сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="21e29-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="21e29-109">Автономная модель развертывания — это специализированная версия автономной модели развертывания, оптимизированная для уменьшения размера развертывания.</span><span class="sxs-lookup"><span data-stu-id="21e29-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="21e29-110">Минимизация размера развертывания является критически важным требованием для некоторых сценариев на стороне клиента, например приложений Blazor.</span><span class="sxs-lookup"><span data-stu-id="21e29-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="21e29-111">В зависимости от сложности приложения, для его запуска требуется только подмножество сборок платформы.</span><span class="sxs-lookup"><span data-stu-id="21e29-111">Depending on the complexity of the application, only a subset of the framework assemblies is required to run the application.</span></span> <span data-ttu-id="21e29-112">Неиспользуемые компоненты библиотеки не нужны, поэтому их можно удалить из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="21e29-112">These unused parts of the library are unnecessary and can be trimmed from the packaged application.</span></span> <span data-ttu-id="21e29-113">Однако существует риск того, что анализ времени сборки приложения может вызвать сбои во время выполнения из-за невозможности надежного анализа различных проблемных шаблонов кода (в основном сосредоточенных на использовании отражения).</span><span class="sxs-lookup"><span data-stu-id="21e29-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="21e29-114">Так как надежность не гарантируется, эта модель развертывания предлагается в качестве предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="21e29-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span> <span data-ttu-id="21e29-115">Модуль анализа времени сборки предоставляет разработчикам предупреждения о проблемных шаблонах кода с предположением, что эти шаблоны кода будут исправлены.</span><span class="sxs-lookup"><span data-stu-id="21e29-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic, with the expectation that these code patterns will be fixed.</span></span> <span data-ttu-id="21e29-116">Там, где это возможно, мы рекомендуем переместить все зависимости отражения среды выполнения в приложении во время сборки с помощью кода, отвечающего тем же требованиям.</span><span class="sxs-lookup"><span data-stu-id="21e29-116">Where possible, we recommend that you move any runtime reflection dependencies in your application to build time by using code that meets the same requirements.</span></span>

<span data-ttu-id="21e29-117">Режим обрезки для приложений можно настроить с помощью TrimMode, и по умолчанию (`copyused`) он будет объединять сборки пакета, используемые в приложении.</span><span class="sxs-lookup"><span data-stu-id="21e29-117">The trim mode for the applications can be configured via the TrimMode and will default (`copyused`) to bundle assemblies that are used in the application.</span></span> <span data-ttu-id="21e29-118">Приложения Blazor WebAssembly используют более агрессивный режим (`link`), который будет обрезать неиспользуемый код в сборках.</span><span class="sxs-lookup"><span data-stu-id="21e29-118">Blazor WebAssembly applications will use a more aggressive mode (`link`) that will trim unused code within assemblies.</span></span> <span data-ttu-id="21e29-119">Предупреждения анализа обрезки предоставляют сведения о шаблонах кода, в которых невозможен полный анализ зависимостей.</span><span class="sxs-lookup"><span data-stu-id="21e29-119">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="21e29-120">Эти предупреждения подавляются по умолчанию и могут быть включены путем установки флага `SuppressTrimAnalysisWarnings` в значение false.</span><span class="sxs-lookup"><span data-stu-id="21e29-120">These warnings are suppressed by default and can be turned on by setting the flag, `SuppressTrimAnalysisWarnings`, to false.</span></span> <span data-ttu-id="21e29-121">Дополнительные сведения о доступных параметрах обрезки можно найти на [странице ILLinker](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span><span class="sxs-lookup"><span data-stu-id="21e29-121">More information on the trim options available can be found at the [ILLinker page](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="21e29-122">Обрезка — это экспериментальная функция в .NET Core 3.1, 5.0, которая доступна _только_ для автономно публикуемых приложений.</span><span class="sxs-lookup"><span data-stu-id="21e29-122">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="21e29-123">Исключение сборок из процесса обрезки</span><span class="sxs-lookup"><span data-stu-id="21e29-123">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="21e29-124">В некоторых случаях функции обрезки не удается обнаружить ссылки.</span><span class="sxs-lookup"><span data-stu-id="21e29-124">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="21e29-125">Например, если в сборке среды выполнения отражение используется либо приложением, либо библиотекой, на которую ссылается приложение, прямые ссылки на эту сборку отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="21e29-125">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="21e29-126">Процессу обрезки неизвестно об этих косвенных ссылках, и он исключит библиотеку из папки опубликованных.</span><span class="sxs-lookup"><span data-stu-id="21e29-126">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="21e29-127">Когда код косвенно ссылается на сборку через отражение, можно исключить сборку из процесса обрезки с помощью параметра `<TrimmerRootAssembly>`.</span><span class="sxs-lookup"><span data-stu-id="21e29-127">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="21e29-128">В следующем примере показано исключение сборки с именем `System.Security` из процесса обрезки.</span><span class="sxs-lookup"><span data-stu-id="21e29-128">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="21e29-129">Обрезка приложения с помощью CLI</span><span class="sxs-lookup"><span data-stu-id="21e29-129">Trim your app - CLI</span></span>

<span data-ttu-id="21e29-130">Выполните обрезку приложения с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="21e29-130">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="21e29-131">При публикации приложения задайте следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="21e29-131">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="21e29-132">Опубликовать как автономное: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="21e29-132">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="21e29-133">Включить обрезку: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="21e29-133">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="21e29-134">В следующем примере показана публикация приложения для Windows в качестве автономного и обрезка выходных данных.</span><span class="sxs-lookup"><span data-stu-id="21e29-134">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<ItemGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <PublishTrimmed>true</PublishTrimmed>
</ItemGroup>
```

<span data-ttu-id="21e29-135">В следующем примере приложение публикуется в режиме агрессивной обрезки, в котором неиспользованный код в сборках будет обрезан, а предупреждения об обрезке будут включены.</span><span class="sxs-lookup"><span data-stu-id="21e29-135">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and  trimmer warnings enabled.</span></span>

```xml
<ItemGroup>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</ItemGroup>
```

<span data-ttu-id="21e29-136">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="21e29-136">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="21e29-137">Обрезка приложения с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21e29-137">Trim your app - Visual Studio</span></span>

<span data-ttu-id="21e29-138">Visual Studio создает многократно используемые профили публикации, которые управляют процессом публикации приложения.</span><span class="sxs-lookup"><span data-stu-id="21e29-138">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="21e29-139">В **обозревателе решений** щелкните правой кнопкой мыши проект, который нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="21e29-139">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="21e29-140">Выберите команду **Опубликовать…** .</span><span class="sxs-lookup"><span data-stu-id="21e29-140">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Обозреватель решений с контекстным меню, где выделен пункт Опубликовать":::

    <span data-ttu-id="21e29-142">Если у вас еще нет профиля публикации, следуйте инструкциям по его созданию и выберите **Папка** в качестве типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="21e29-142">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="21e29-143">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="21e29-143">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Профиль публикации Visual Studio с кнопкой Изменить":::

01. <span data-ttu-id="21e29-145">В диалоговом окне **Параметры профиля** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="21e29-145">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="21e29-146">Параметру **Режим развертывания** задайте значение **Автономное**.</span><span class="sxs-lookup"><span data-stu-id="21e29-146">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="21e29-147">В качестве значения параметра **Целевая среда выполнения** укажите платформу, на которую будет выполнена публикация.</span><span class="sxs-lookup"><span data-stu-id="21e29-147">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="21e29-148">Выберите **Обрезать неиспользуемые сборки (в предварительной версии)** .</span><span class="sxs-lookup"><span data-stu-id="21e29-148">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="21e29-149">Нажмите кнопку **Сохранить**, чтобы сохранить параметры и вернуться в диалоговое окно **Публикация**.</span><span class="sxs-lookup"><span data-stu-id="21e29-149">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Диалоговое окно параметров профиля с выделенными параметрами для режима развертывания, целевой среды выполнения и обрезки неиспользуемых сборок.":::

01. <span data-ttu-id="21e29-151">Чтобы опубликовать обрезанное приложение, нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="21e29-151">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="21e29-152">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="21e29-152">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="21e29-153">Обрезка приложения с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="21e29-153">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="21e29-154">В Visual Studio для Mac отсутствует возможность обрезки приложения во время публикации.</span><span class="sxs-lookup"><span data-stu-id="21e29-154">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="21e29-155">Вам потребуется вручную опубликовать приложение, выполнив инструкции в разделе [Образка приложения с помощью CLI](#trim-your-app---cli).</span><span class="sxs-lookup"><span data-stu-id="21e29-155">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="21e29-156">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="21e29-156">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21e29-157">См. также</span><span class="sxs-lookup"><span data-stu-id="21e29-157">See also</span></span>

- <span data-ttu-id="21e29-158">[Развертывание приложений .NET Core](index.md)</span><span class="sxs-lookup"><span data-stu-id="21e29-158">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="21e29-159">[Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="21e29-159">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="21e29-160">[Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="21e29-160">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="21e29-161">[Команда dotnet publish](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="21e29-161">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
