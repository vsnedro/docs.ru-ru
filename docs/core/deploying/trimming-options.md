---
title: Параметры обрезки
description: Узнайте, как управлять обрезкой автономных приложений.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 5597d4cdb9e8e96dcec6545e039d43295ca991bd
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142262"
---
# <a name="trimming-options"></a><span data-ttu-id="4a22a-103">Параметры обрезки</span><span class="sxs-lookup"><span data-stu-id="4a22a-103">Trimming options</span></span>

<span data-ttu-id="4a22a-104">Следующие свойства и элементы MSBuild влияют на поведение [обрезанных автономных развертываний](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="4a22a-104">The following MSBuild properties and items influence the behavior of [trimmed self-contained deployments](trim-self-contained.md).</span></span> <span data-ttu-id="4a22a-105">Некоторые параметры упоминают `ILLink`, то есть имя базового инструмента, реализующего обрезку.</span><span class="sxs-lookup"><span data-stu-id="4a22a-105">Some of the options mention `ILLink`, which is the name of the underlying tool that implements trimming.</span></span> <span data-ttu-id="4a22a-106">Дополнительные сведения о программе командной строки `ILLink` см. в разделе [Параметры illink](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span><span class="sxs-lookup"><span data-stu-id="4a22a-106">More information about the `ILLink` command-line tool can be found at [illink options](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span></span>

## <a name="enable-trimming"></a><span data-ttu-id="4a22a-107">Включение обрезки</span><span class="sxs-lookup"><span data-stu-id="4a22a-107">Enable trimming</span></span>

- `<PublishTrimmed>true</PublishTrimmed>`

   <span data-ttu-id="4a22a-108">Включите обрезку во время публикации с параметрами по умолчанию, определенными пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="4a22a-108">Enable trimming during publish, with the default settings defined by the SDK.</span></span>

<span data-ttu-id="4a22a-109">При использовании `Microsoft.NET.Sdk` выполняется обрезка сборок платформы из пакета среды выполнения netcoreapp на уровне сборки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-109">When using `Microsoft.NET.Sdk`, this will perform assembly-level trimming of the framework assemblies from the netcoreapp runtime pack.</span></span> <span data-ttu-id="4a22a-110">Код приложения и библиотеки, отличные от платформы, не обрезаются.</span><span class="sxs-lookup"><span data-stu-id="4a22a-110">Application code and non-framework libraries are not trimmed.</span></span> <span data-ttu-id="4a22a-111">Другие пакеты SDK могут определять разные значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4a22a-111">Other SDKs may define different defaults.</span></span>

## <a name="trimming-granularity"></a><span data-ttu-id="4a22a-112">Степень детализации обрезки</span><span class="sxs-lookup"><span data-stu-id="4a22a-112">Trimming granularity</span></span>

<span data-ttu-id="4a22a-113">Следующие параметры степени детализации управляют тем, насколько агрессивно отбрасываются неиспользуемые IL.</span><span class="sxs-lookup"><span data-stu-id="4a22a-113">The following granularity settings control how aggressively unused IL is discarded.</span></span> <span data-ttu-id="4a22a-114">Это можно задать как свойство или как метаданные в [отдельной сборке](#Trimmed-assemblies).</span><span class="sxs-lookup"><span data-stu-id="4a22a-114">This can be set as a property, or as metadata on an [individual assembly](#Trimmed-assemblies).</span></span>

- `<TrimMode>copyused</TrimMode>`

   <span data-ttu-id="4a22a-115">Включите функцию обрезки на уровне сборки, которая будет сохранять всю сборку, если какая-либо ее часть используется (статически понятным образом).</span><span class="sxs-lookup"><span data-stu-id="4a22a-115">Enable assembly-level trimming, which will keep an entire assembly if any part of it is used (in a statically-understood way).</span></span>

- `<TrimMode>link</TrimMode>`

    <span data-ttu-id="4a22a-116">Включите функцию обрезки на уровне элементов, которая удаляет неиспользуемые элементы из типов.</span><span class="sxs-lookup"><span data-stu-id="4a22a-116">Enable member-level trimming, which removes unused members from types.</span></span>

<span data-ttu-id="4a22a-117">Сборки с метаданными `<IsTrimmable>true</IsTrimmable>`, но без явного `TrimMode` будут использовать глобальную `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-117">Assemblies with `<IsTrimmable>true</IsTrimmable>` metadata but no explicit `TrimMode` will use the global `TrimMode`.</span></span> <span data-ttu-id="4a22a-118">`TrimMode` по умолчанию для `Microsoft.NET.Sdk` — `copyused`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-118">The default `TrimMode` for `Microsoft.NET.Sdk` is `copyused`.</span></span>

## <a name="trimmed-assemblies"></a><span data-ttu-id="4a22a-119">Обрезанные сборки</span><span class="sxs-lookup"><span data-stu-id="4a22a-119">Trimmed assemblies</span></span>

<span data-ttu-id="4a22a-120">При публикации обрезанного приложения пакет SDK выдает `ItemGroup` с именем `ManagedAssemblyToLink`, который представляет набор файлов для обработки обрезки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-120">When publishing a trimmed app, the SDK computes an `ItemGroup` called `ManagedAssemblyToLink` that represents the set of files to be processed for trimming.</span></span> <span data-ttu-id="4a22a-121">`ManagedAssemblyToLink` может иметь метаданные, управляющие поведением обрезки для каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-121">`ManagedAssemblyToLink` may have metadata that controls the trimming behavior per assembly.</span></span> <span data-ttu-id="4a22a-122">Чтобы задать эти метаданные, создайте целевой объект, выполняемый перед встроенным целевым объектом `PrepareForILLink`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-122">To set this metadata, create a target that runs before the built-in `PrepareForILLink` target.</span></span> <span data-ttu-id="4a22a-123">В этом примере показано, как включить обрезку `MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-123">This example shows how to enable trimming of `MyAssembly`:</span></span>

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

<span data-ttu-id="4a22a-124">Не добавляйте и не удаляйте элементы в `ManagedAssemblyToLink`, так как пакет SDK рассчитывает этот набор во время публикации и полагает, что он не изменяется.</span><span class="sxs-lookup"><span data-stu-id="4a22a-124">Do not add or remove items to/from `ManagedAssemblyToLink`, because the SDK computes this set during publish and expects it not to change.</span></span> <span data-ttu-id="4a22a-125">Поддерживаются следующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="4a22a-125">The supported metadata is:</span></span>

- `<IsTrimmable>true</IsTrimmable>`

  <span data-ttu-id="4a22a-126">Управление тем, обрезана ли данная сборка.</span><span class="sxs-lookup"><span data-stu-id="4a22a-126">Control whether the given assembly is trimmed.</span></span>

- <span data-ttu-id="4a22a-127">`<TrimMode>copyused</TrimMode>` или `<TrimMode>link</TrimMode>`</span><span class="sxs-lookup"><span data-stu-id="4a22a-127">`<TrimMode>copyused</TrimMode>` or `<TrimMode>link</TrimMode>`</span></span>

  <span data-ttu-id="4a22a-128">Управление [степенью детализации](#Trimming-granularity) этой сборки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-128">Control the [trimming granularity](#Trimming-granularity) of this assembly.</span></span> <span data-ttu-id="4a22a-129">Имеет приоритет над глобальным `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-129">This takes precedence over the global `TrimMode`.</span></span> <span data-ttu-id="4a22a-130">Установка `TrimMode` для сборки подразумевает `<IsTrimmable>true</IsTrimmable>`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-130">Setting `TrimMode` on an assembly implies `<IsTrimmable>true</IsTrimmable>`.</span></span>

## <a name="root-assemblies"></a><span data-ttu-id="4a22a-131">Корневые сборки</span><span class="sxs-lookup"><span data-stu-id="4a22a-131">Root assemblies</span></span>

<span data-ttu-id="4a22a-132">Все сборки, не имеющие `<IsTrimmable>true</IsTrimmable>`, считаются корневыми для анализа. Это означает, что они и все статически понятные зависимости будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="4a22a-132">All assemblies which do not have `<IsTrimmable>true</IsTrimmable>` are considered roots for the analysis, which means that they and all of their statically understood dependencies will be kept.</span></span> <span data-ttu-id="4a22a-133">Дополнительные сборки могут быть корневыми по имени (без расширения `.dll`).</span><span class="sxs-lookup"><span data-stu-id="4a22a-133">Additional assemblies may be "rooted" by name (without the `.dll` extension):</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a><span data-ttu-id="4a22a-134">Корневые дескрипторы</span><span class="sxs-lookup"><span data-stu-id="4a22a-134">Root descriptors</span></span>

<span data-ttu-id="4a22a-135">Другой способ указания корней для анализа — использование XML-файла, в котором используется компоновщик [формата дескриптора](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span><span class="sxs-lookup"><span data-stu-id="4a22a-135">Another way to specify roots for analysis is using an XML file that uses the linker [descriptor format](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span></span> <span data-ttu-id="4a22a-136">Это позволяет использовать корневые члены вместо целой сборки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-136">This lets you root specific members instead of a whole assembly.</span></span>

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

<span data-ttu-id="4a22a-137">Например, `MyRoots.xml` может быть корневым для конкретного метода, к которому приложение обращается динамически.</span><span class="sxs-lookup"><span data-stu-id="4a22a-137">For example, `MyRoots.xml` might root a specific method that is dynamically accessed by the application:</span></span>

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a><span data-ttu-id="4a22a-138">Предупреждения при анализе</span><span class="sxs-lookup"><span data-stu-id="4a22a-138">Analysis warnings</span></span>

<span data-ttu-id="4a22a-139">Обрезка приведет к удалению IL, который не является статически достижимым.</span><span class="sxs-lookup"><span data-stu-id="4a22a-139">Trimming will remove IL that is not statically reachable.</span></span> <span data-ttu-id="4a22a-140">Приложения, использующие отражение или другие шаблоны, которые создают динамические зависимости, могут быть разорваны путем обрезки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-140">Apps that use reflection or other patterns that create dynamic dependencies may be broken by trimming.</span></span> <span data-ttu-id="4a22a-141">Чтобы получать предупреждения об этих шаблонах, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4a22a-141">To warn about such patterns:</span></span>

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    <span data-ttu-id="4a22a-142">Включите предупреждения при анализе обрезки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-142">Enable trim analysis warnings.</span></span>

<span data-ttu-id="4a22a-143">Сюда будут включены предупреждения обо всем приложении, включая собственный код, код библиотеки и код платформы.</span><span class="sxs-lookup"><span data-stu-id="4a22a-143">This will include warnings about the entire app, including your own code, library code, and framework code.</span></span>

## <a name="warning-versions"></a><span data-ttu-id="4a22a-144">Версии предупреждений</span><span class="sxs-lookup"><span data-stu-id="4a22a-144">Warning versions</span></span>

<span data-ttu-id="4a22a-145">При анализе обрезки учитывается свойство [`AnalysisLevel`](../project-sdk/msbuild-props.md#AnalysisLevel), которое управляет версией предупреждений при анализе для пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="4a22a-145">Trim analysis respects the [`AnalysisLevel`](../project-sdk/msbuild-props.md#AnalysisLevel) property that controls the version of analysis warnings across the SDK.</span></span> <span data-ttu-id="4a22a-146">Существует еще одно свойство, которое управляет версией предупреждений при анализе обрезки независимо (аналогично `WarningLevel` для компилятора).</span><span class="sxs-lookup"><span data-stu-id="4a22a-146">There is another property that controls the version of trim analysis warnings independently (similar to `WarningLevel` for the compiler):</span></span>

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    <span data-ttu-id="4a22a-147">Настройте отображение только предупреждений заданного или нижнего уровня.</span><span class="sxs-lookup"><span data-stu-id="4a22a-147">Emit only warnings of the given level or lower.</span></span> <span data-ttu-id="4a22a-148">Это может быть `9999` для включения всех версий предупреждений.</span><span class="sxs-lookup"><span data-stu-id="4a22a-148">This can be `9999` to include all warning versions.</span></span>

## <a name="suppressing-warnings"></a><span data-ttu-id="4a22a-149">Подавление предупреждений</span><span class="sxs-lookup"><span data-stu-id="4a22a-149">Suppressing warnings</span></span>

<span data-ttu-id="4a22a-150">Отдельные [коды предупреждений](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) можно подавлять с помощью стандартных свойств MSBuild, которые учитываются цепочкой инструментов, включая `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` и `TreatWarningsAsErrors`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-150">Individual [warning codes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) can be suppressed using the usual MSBuild properties respected by the toolchain, including `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors`, and `TreatWarningsAsErrors`.</span></span> <span data-ttu-id="4a22a-151">Существует дополнительный параметр, который управляет поведением предупреждения как ошибки ILLink отдельно.</span><span class="sxs-lookup"><span data-stu-id="4a22a-151">There is an additional option that controls the ILLink warn-as-error behavior independently:</span></span>

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    <span data-ttu-id="4a22a-152">Не обрабатывайте предупреждения ILLink как ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a22a-152">Don't treat ILLink warnings as errors.</span></span> <span data-ttu-id="4a22a-153">Это может быть полезно, чтобы не включать предупреждения при анализе обрезки в ошибки при обработке предупреждений компилятора как ошибок в глобальном масштабе.</span><span class="sxs-lookup"><span data-stu-id="4a22a-153">This may be useful to avoid turning trim analysis warnings into errors when treating compiler warnings as errors globally.</span></span>

## <a name="removing-symbols"></a><span data-ttu-id="4a22a-154">Удаление символов</span><span class="sxs-lookup"><span data-stu-id="4a22a-154">Removing symbols</span></span>

<span data-ttu-id="4a22a-155">Символы, как правило, усекаются, чтобы соответствовать обрезанным сборкам.</span><span class="sxs-lookup"><span data-stu-id="4a22a-155">Symbols will normally be trimmed to match the trimmed assemblies.</span></span> <span data-ttu-id="4a22a-156">Можно также удалить все символы.</span><span class="sxs-lookup"><span data-stu-id="4a22a-156">You can also remove all symbols:</span></span>

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    <span data-ttu-id="4a22a-157">Удалите символы из обрезанного приложения, включая внедренные PDB-файлы и отдельные PDB.</span><span class="sxs-lookup"><span data-stu-id="4a22a-157">Remove symbols from the trimmed application, including embedded PDBs and separate PDB files.</span></span> <span data-ttu-id="4a22a-158">Это относится как к коду приложения, так и к любым зависимостям, которые входят в состав символов.</span><span class="sxs-lookup"><span data-stu-id="4a22a-158">This applies to both the application code and any dependencies that come with symbols.</span></span>

<span data-ttu-id="4a22a-159">Пакет SDK также позволяет отключить поддержку отладчика, используя свойство `DebuggerSupport`.</span><span class="sxs-lookup"><span data-stu-id="4a22a-159">The SDK also makes it possible to disable debugger support using the property `DebuggerSupport`.</span></span> <span data-ttu-id="4a22a-160">Если поддержка отладчика отключена, то при обрезке символы автоматически удаляются (`TrimmerRemoveSymbols` по умолчанию принимает значение true).</span><span class="sxs-lookup"><span data-stu-id="4a22a-160">When debugger support is disabled, trimming will remove symbols automatically (`TrimmerRemoveSymbols` will default to true).</span></span>
