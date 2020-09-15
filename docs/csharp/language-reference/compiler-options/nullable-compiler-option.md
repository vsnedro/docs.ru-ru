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
ms.openlocfilehash: f9c6c204d2563865f741c6ddb4644eb56f956c12
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125050"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="a62e8-103">-nullable (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a62e8-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="a62e8-104">Параметр **-nullable** позволяет указать требуемый контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-104">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="a62e8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a62e8-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="a62e8-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a62e8-106">Arguments</span></span>

<span data-ttu-id="a62e8-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a62e8-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="a62e8-108">При указании `+` или просто параметра **-nullable** компилятор включит контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-108">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="a62e8-109">При указании `-`, который действует, если не указан параметр **-nullable**, отключается контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-109">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="a62e8-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="a62e8-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="a62e8-111">Указывает параметр контекста, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-111">Specifies the nullable context option.</span></span> <span data-ttu-id="a62e8-112">Используется аналогично `+` или `-`, чтобы включать и отключать контекст, но обеспечивает больший уровень детализации для контекста, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="a62e8-113">Аргумент `enable`, который действует так же, как параметр **-nullable**, включает контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="a62e8-114">При указании `disable` будет отключен контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="a62e8-115">При указании аргумента `warnings` **-nullable:warnings** будет включен контекст предупреждения, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="a62e8-116">При указании аргумента `annotations`, **-nullable:annotations**, будет включен контекст с заметками о допустимости значений NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="a62e8-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a62e8-117">Remarks</span></span>

<span data-ttu-id="a62e8-118">Анализ потока используется для определения допустимости значений NULL в переменных в исполняемом коде.</span><span class="sxs-lookup"><span data-stu-id="a62e8-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="a62e8-119">Выводимая допустимость переменной значения NULL не зависит от объявленной в переменной допустимости значения NULL.</span><span class="sxs-lookup"><span data-stu-id="a62e8-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="a62e8-120">Вызовы методов анализируются, даже если они условно опущены.</span><span class="sxs-lookup"><span data-stu-id="a62e8-120">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="a62e8-121">Например, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="a62e8-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="a62e8-122">Вызов методов, снабженных следующими атрибутами, также повлияет на анализ потока:</span><span class="sxs-lookup"><span data-stu-id="a62e8-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="a62e8-123">Простые предварительные условия: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="a62e8-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="a62e8-124">Простые постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="a62e8-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="a62e8-125">Условные постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="a62e8-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="a62e8-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (например, `DoesNotReturnIf(false)` для <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) и <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="a62e8-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="a62e8-127">Постусловия элемента: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> и <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="a62e8-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="a62e8-128">Установка данного параметра компилятора в проекте</span><span class="sxs-lookup"><span data-stu-id="a62e8-128">To set this compiler option in a project</span></span>

<span data-ttu-id="a62e8-129">Измените файл *CSPROJ*, добавив тег `<Nullable>` в иерархию `Project/PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="a62e8-129">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="a62e8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a62e8-130">See also</span></span>

- [<span data-ttu-id="a62e8-131">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="a62e8-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a62e8-132">Ссылочные типы, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="a62e8-132">Nullable reference types</span></span>](../../nullable-references.md)
