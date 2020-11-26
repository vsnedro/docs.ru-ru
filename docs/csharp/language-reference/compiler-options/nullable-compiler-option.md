---
description: -nullable (параметры компилятора C#)
title: -nullable (параметры компилятора C#)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 68857d0cb4d0cd1177506e0b7ce897d2cfc3aa5b
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099228"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="e8548-103">-nullable (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="e8548-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="e8548-104">Параметр **-nullable** позволяет указать контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-104">The **-nullable** option lets you specify the nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8548-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8548-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="e8548-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e8548-106">Arguments</span></span>

<span data-ttu-id="e8548-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e8548-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="e8548-108">При указании `+` или параметра **-nullable** компилятор включит контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-108">Specifying `+`, or **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="e8548-109">При указании `-`, который действует, если не указан параметр **-nullable**, отключается контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-109">Specifying `-`, which is in effect if you don't specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="e8548-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="e8548-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="e8548-111">Указывает параметр контекста, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-111">Specifies the nullable context option.</span></span> <span data-ttu-id="e8548-112">Используется аналогично `+` или `-`, чтобы включать и отключать контекст, но обеспечивает больший уровень детализации для контекста, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="e8548-113">Аргумент `enable`, который действует так же, как параметр **-nullable**, включает контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="e8548-114">При указании `disable` будет отключен контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="e8548-115">При указании аргумента `warnings` **-nullable:warnings** будет включен контекст предупреждения, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="e8548-116">При указании аргумента `annotations`, **-nullable:annotations**, будет включен контекст с заметками о допустимости значений NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8548-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8548-117">Remarks</span></span>

<span data-ttu-id="e8548-118">Анализ потока используется для определения допустимости значений NULL в переменных в исполняемом коде.</span><span class="sxs-lookup"><span data-stu-id="e8548-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="e8548-119">Выводимая допустимость переменной значения NULL не зависит от объявленной в переменной допустимости значения NULL.</span><span class="sxs-lookup"><span data-stu-id="e8548-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="e8548-120">Вызовы методов анализируются, даже если они условно опущены.</span><span class="sxs-lookup"><span data-stu-id="e8548-120">Method calls are analyzed even when they're conditionally omitted.</span></span> <span data-ttu-id="e8548-121">Например, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="e8548-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="e8548-122">Вызов методов, снабженных следующими атрибутами, также повлияет на анализ потока:</span><span class="sxs-lookup"><span data-stu-id="e8548-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="e8548-123">Простые предварительные условия: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="e8548-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="e8548-124">Простые постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="e8548-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="e8548-125">Условные постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="e8548-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="e8548-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (например, `DoesNotReturnIf(false)` для <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) и <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="e8548-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="e8548-127">Постусловия элемента: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> и <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="e8548-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8548-128">Глобальный контекст, допускающий значения NULL, не применяется для созданных файлов кода.</span><span class="sxs-lookup"><span data-stu-id="e8548-128">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="e8548-129">Независимо от этого параметра, контекст, допускающий значение NULL, *отключен* для любого исходного файла, помеченного как созданный.</span><span class="sxs-lookup"><span data-stu-id="e8548-129">Regardless of this setting, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="e8548-130">Существует четыре способа пометки файла как созданного:</span><span class="sxs-lookup"><span data-stu-id="e8548-130">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="e8548-131">В файле. editorconfig укажите `generated_code = true` в разделе, который применяется к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="e8548-131">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="e8548-132">Вставьте `<auto-generated>` или `<auto-generated/>` в комментарий в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="e8548-132">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="e8548-133">Он может находиться в любой строке комментария, однако блок комментариев должен быть первым элементом в файле.</span><span class="sxs-lookup"><span data-stu-id="e8548-133">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="e8548-134">Имя файла следует начинать с *TemporaryGeneratedFile_*</span><span class="sxs-lookup"><span data-stu-id="e8548-134">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="e8548-135">В конце имени файла следует указать *.designer.cs*, *.generated.cs*, *.g.cs* или *.g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="e8548-135">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="e8548-136">Генераторы могут явно использовать директиву препроцессора [`#nullable`](../preprocessor-directives/preprocessor-nullable.md).</span><span class="sxs-lookup"><span data-stu-id="e8548-136">Generators can opt-in using the [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="e8548-137">Установка данного параметра компилятора в проекте</span><span class="sxs-lookup"><span data-stu-id="e8548-137">To set this compiler option in a project</span></span>

<span data-ttu-id="e8548-138">Измените файл *CSPROJ*, добавив тег `<Nullable>` в иерархию `Project/PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="e8548-138">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="e8548-139">См. также</span><span class="sxs-lookup"><span data-stu-id="e8548-139">See also</span></span>

- [<span data-ttu-id="e8548-140">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="e8548-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e8548-141">Директивы препроцессора`#nullable`</span><span class="sxs-lookup"><span data-stu-id="e8548-141">`#nullable` preprocessor directive</span></span>](../preprocessor-directives/preprocessor-nullable.md)
- [<span data-ttu-id="e8548-142">Ссылочные типы, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="e8548-142">Nullable reference types</span></span>](../../nullable-references.md)
