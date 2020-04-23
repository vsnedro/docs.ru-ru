---
title: Обрезка автономных приложений
description: Сведения об обрезке автономных приложений для уменьшения их размера. .NET Core объединяет среду выполнения с автономно публикуемым приложением и обычно содержит больше компонентов среды выполнения, чем необходимо.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242928"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="37d10-104">Обрезка автономных развертываний и исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="37d10-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="37d10-105">При публикации автономного приложения среда выполнения .NET Core объединяется с приложением.</span><span class="sxs-lookup"><span data-stu-id="37d10-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="37d10-106">В этом случае в упакованное приложение добавляется значительный объем содержимого.</span><span class="sxs-lookup"><span data-stu-id="37d10-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="37d10-107">Когда дело доходит до развертывания приложения, размер часто является важным фактором.</span><span class="sxs-lookup"><span data-stu-id="37d10-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="37d10-108">Как правило, разработчики приложений стремятся максимально уменьшить размер пакета приложения.</span><span class="sxs-lookup"><span data-stu-id="37d10-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="37d10-109">В зависимости от сложности приложения для его запуска и работы требуется только подмножество среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="37d10-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="37d10-110">Неиспользуемые компоненты среды выполнения не нужны, поэтому их можно удалить из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="37d10-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="37d10-111">Функция обрезки проверяет двоичные файлы приложения, чтобы найти требуемые сборки среды выполнения и построить соответствующий граф.</span><span class="sxs-lookup"><span data-stu-id="37d10-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="37d10-112">Оставшиеся сборки среды выполнения, на которые отсутствуют ссылки, исключаются.</span><span class="sxs-lookup"><span data-stu-id="37d10-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="37d10-113">Обрезка — это экспериментальная функция в .NET Core 3.1, которая доступна _только_ для автономно публикуемых приложений.</span><span class="sxs-lookup"><span data-stu-id="37d10-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="37d10-114">Исключение сборок из процесса обрезки</span><span class="sxs-lookup"><span data-stu-id="37d10-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="37d10-115">В некоторых случаях функции обрезки не удается обнаружить ссылки.</span><span class="sxs-lookup"><span data-stu-id="37d10-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="37d10-116">Например, если в сборке среды выполнения отражение используется либо приложением, либо библиотекой, на которую ссылается приложение, прямые ссылки на эту сборку отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="37d10-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="37d10-117">Процессу обрезки неизвестно об этих косвенных ссылках, и он исключит библиотеку из папки опубликованных.</span><span class="sxs-lookup"><span data-stu-id="37d10-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="37d10-118">Когда код косвенно ссылается на сборку через отражение, можно исключить сборку из процесса обрезки с помощью параметра `<TrimmerRootAssembly>`.</span><span class="sxs-lookup"><span data-stu-id="37d10-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="37d10-119">В следующем примере показано исключение сборки с именем `System.Security` из процесса обрезки.</span><span class="sxs-lookup"><span data-stu-id="37d10-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="37d10-120">Обрезка приложения с помощью CLI</span><span class="sxs-lookup"><span data-stu-id="37d10-120">Trim your app - CLI</span></span>

<span data-ttu-id="37d10-121">Выполните обрезку приложения с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="37d10-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="37d10-122">При публикации приложения задайте следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="37d10-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="37d10-123">Опубликовать как автономное: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="37d10-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="37d10-124">Отключить однофайловую публикацию: `-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="37d10-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="37d10-125">Включить обрезку: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="37d10-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="37d10-126">В следующем примере показана публикация приложения для Windows 10 в качестве автономного и обрезка выходных данных.</span><span class="sxs-lookup"><span data-stu-id="37d10-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="37d10-127">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="37d10-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="37d10-128">Обрезка приложения с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37d10-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="37d10-129">Visual Studio создает многократно используемые профили публикации, которые управляют процессом публикации приложения.</span><span class="sxs-lookup"><span data-stu-id="37d10-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="37d10-130">В **обозревателе решений** щелкните правой кнопкой мыши проект, который нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="37d10-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="37d10-131">Выберите команду **Опубликовать…** .</span><span class="sxs-lookup"><span data-stu-id="37d10-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Обозреватель решений с контекстным меню, где выделен пункт "Опубликовать"":::

    <span data-ttu-id="37d10-133">Если у вас еще нет профиля публикации, следуйте инструкциям по его созданию и выберите **Папка** в качестве типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="37d10-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="37d10-134">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="37d10-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Профиль публикации Visual Studio с кнопкой "Изменить"":::

01. <span data-ttu-id="37d10-136">В диалоговом окне **Параметры профиля** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="37d10-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="37d10-137">Параметру **Режим развертывания** задайте значение **Автономное**.</span><span class="sxs-lookup"><span data-stu-id="37d10-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="37d10-138">В качестве значения параметра **Целевая среда выполнения** укажите платформу, на которую будет выполнена публикация.</span><span class="sxs-lookup"><span data-stu-id="37d10-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="37d10-139">Выберите **Обрезать неиспользуемые сборки (в предварительной версии)** .</span><span class="sxs-lookup"><span data-stu-id="37d10-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="37d10-140">Нажмите кнопку **Сохранить**, чтобы сохранить параметры и вернуться в диалоговое окно **Публикация**.</span><span class="sxs-lookup"><span data-stu-id="37d10-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Диалоговое окно параметров профиля с выделенными параметрами для режима развертывания, целевой среды выполнения и обрезки неиспользуемых сборок.":::

01. <span data-ttu-id="37d10-142">Чтобы опубликовать обрезанное приложение, нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="37d10-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="37d10-143">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="37d10-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="37d10-144">Обрезка приложения с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="37d10-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="37d10-145">В Visual Studio для Mac отсутствует возможность обрезки приложения во время публикации.</span><span class="sxs-lookup"><span data-stu-id="37d10-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="37d10-146">Вам потребуется вручную опубликовать приложение, выполнив инструкции в разделе [Образка приложения с помощью CLI](#trim-your-app---cli).</span><span class="sxs-lookup"><span data-stu-id="37d10-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="37d10-147">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="37d10-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37d10-148">См. также</span><span class="sxs-lookup"><span data-stu-id="37d10-148">See also</span></span>

- <span data-ttu-id="37d10-149">[Развертывание приложений .NET Core](index.md)</span><span class="sxs-lookup"><span data-stu-id="37d10-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="37d10-150">[Публикация приложений .NET Core с помощью .NET Core CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="37d10-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="37d10-151">[Публикация приложений .NET Core с помощью Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="37d10-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="37d10-152">[Команда dotnet publish](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="37d10-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
