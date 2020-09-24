---
ms.openlocfilehash: edff55d540f08e8a9fd4d0687aaf6bd963ee3a84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539530"
---
### <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="b4d1c-101">Blazor: Открытые поля только для чтения RenderTreeFrame стали свойствами</span><span class="sxs-lookup"><span data-stu-id="b4d1c-101">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="b4d1c-102">В ASP.NET Core 3.0 и 3.1 структура <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> содержит различные поля `readonly public`, включая <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> и другие.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-102">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="b4d1c-103">В ASP.NET Core 5.0 RC1 и более поздних версиях все поля `readonly public` изменились на свойства `readonly public`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-103">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="b4d1c-104">Это изменение не затронет многих разработчиков по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-104">This change won't affect many developers because:</span></span>

* <span data-ttu-id="b4d1c-105">Все приложения или библиотеки, которые просто используют файлы `.razor` (или даже выполняемые вручную вызовы <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder>) для определения их компонентов, не ссылаются на этот тип напрямую.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-105">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="b4d1c-106">Сам тип `RenderTreeFrame` рассматривается как компонент реализации, не предназначенный для использования вне платформы.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-106">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="b4d1c-107">В состав ASP.NET Core 3.0 и более поздних версий входит анализатор, который выдает предупреждения компилятора в случае непосредственного использования типа.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-107">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="b4d1c-108">Даже если вы ссылаетесь на `RenderTreeFrame` напрямую, это изменение нарушает двоичные файлы, но не нарушает исходный код.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-108">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="b4d1c-109">То есть существующий исходный код будет правильно компилироваться и работать.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-109">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="b4d1c-110">Ошибка возникнет только при компиляции на платформе .NET Core 3.x и последующем запуске этих двоичных файлов на платформе .NET 5.0 RC1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-110">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="b4d1c-111">Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span><span class="sxs-lookup"><span data-stu-id="b4d1c-111">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b4d1c-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b4d1c-112">Version introduced</span></span>

<span data-ttu-id="b4d1c-113">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="b4d1c-113">5.0 RC1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b4d1c-114">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="b4d1c-114">Old behavior</span></span>

<span data-ttu-id="b4d1c-115">Открытые члены в `RenderTreeFrame` определяются как поля.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-115">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="b4d1c-116">Например, `renderTreeFrame.Sequence` и `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-116">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b4d1c-117">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="b4d1c-117">New behavior</span></span>

<span data-ttu-id="b4d1c-118">Открытые члены в `RenderTreeFrame` определяются как свойства с теми же именами, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-118">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="b4d1c-119">Например, `renderTreeFrame.Sequence` и `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-119">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="b4d1c-120">Если более старый предварительно скомпилированный код не был перекомпилирован с момента этого изменения, может возникнуть исключение, похожее на *MissingFieldException. Поле не найдено: "Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType"* .</span><span class="sxs-lookup"><span data-stu-id="b4d1c-120">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b4d1c-121">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="b4d1c-121">Reason for change</span></span>

<span data-ttu-id="b4d1c-122">Это изменение было необходимо для реализации важных улучшений производительности в отрисовке компонентов Blazor в ASP.NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-122">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="b4d1c-123">Поддерживаются те же уровни безопасности и инкапсуляции.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-123">The same levels of safety and encapsulation are maintained.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b4d1c-124">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b4d1c-124">Recommended action</span></span>

<span data-ttu-id="b4d1c-125">Это изменение не затрагивает большинство разработчиков Blazor.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-125">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="b4d1c-126">Оно, скорее всего, повлияет на авторов библиотек и пакетов, но только в редких случаях.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-126">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="b4d1c-127">В частности, если вы:</span><span class="sxs-lookup"><span data-stu-id="b4d1c-127">Specifically, if you're developing:</span></span>

* <span data-ttu-id="b4d1c-128">Разрабатываете приложение и используете ASP.NET Core 3.x или выполняете обновление до 5.0 RC1 или более поздней версии, вам не нужно изменять собственный код.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-128">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="b4d1c-129">Однако если существует зависимость от библиотеки, которая обновлена с учетом этого изменения, необходимо выполнить обновление до более новой версии этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-129">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="b4d1c-130">Создаете библиотеку и хотите поддерживать только ASP.NET Core 5.0 RC1 или более поздние версии, никаких действий выполнять не требуется.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-130">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="b4d1c-131">Просто убедитесь, что в файле проекта объявлено значение `<TargetFramework>` `net5.0` или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-131">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="b4d1c-132">Создаете библиотеку и хотите поддерживать ASP.NET Core 3 x *и* 5.0, определите, считывает ли код элементы `RenderTreeFrame`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-132">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="b4d1c-133">Например, оцените `someRenderTreeFrame.FrameType`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-133">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="b4d1c-134">Большинство библиотек, включая библиотеки, содержащие компоненты `.razor`, не считывают элементы `RenderTreeFrame`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-134">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="b4d1c-135">В этом случае никаких действий выполнять не требуется.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-135">In this case, no action is needed.</span></span>
  * <span data-ttu-id="b4d1c-136">Однако если ваша библиотека считывает элементы, вам потребуется несколько целевых платформ для поддержки `netstandard2.1` и `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-136">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="b4d1c-137">Примените следующие изменения в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-137">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="b4d1c-138">Замените существующий элемент `<TargetFramework>` на `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-138">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="b4d1c-139">Используйте ссылку на условный пакет `Microsoft.AspNetCore.Components`, чтобы учесть обе версии, которые требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="b4d1c-139">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="b4d1c-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="b4d1c-140">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="b4d1c-141">Дополнительные пояснения см. на странице [сравнения, где @jsakamoto уже обновил библиотеку `Toolbelt.Blazor.HeadElement`](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span><span class="sxs-lookup"><span data-stu-id="b4d1c-141">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

#### <a name="category"></a><span data-ttu-id="b4d1c-142">Категория</span><span class="sxs-lookup"><span data-stu-id="b4d1c-142">Category</span></span>

<span data-ttu-id="b4d1c-143">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b4d1c-143">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b4d1c-144">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b4d1c-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
