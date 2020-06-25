---
title: -nullable (параметры компилятора C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 7454bb316507c3aaea208094127552712421dff6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990126"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="a9400-102">-nullable (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a9400-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="a9400-103">Параметр **-nullable** позволяет указать требуемый контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9400-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9400-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="a9400-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a9400-105">Arguments</span></span>

<span data-ttu-id="a9400-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a9400-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="a9400-107">При указании `+` или просто параметра **-nullable** компилятор включит контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="a9400-108">При указании `-`, который действует, если не указан параметр **-nullable**, отключается контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="a9400-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="a9400-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="a9400-110">Указывает параметр контекста, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-110">Specifies the nullable context option.</span></span> <span data-ttu-id="a9400-111">Используется аналогично `+` или `-`, чтобы включать и отключать контекст, но обеспечивает больший уровень детализации для контекста, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="a9400-112">Аргумент `enable`, который действует так же, как параметр **-nullable**, включает контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="a9400-113">При указании `disable` будет отключен контекст, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="a9400-114">При указании аргумента `warnings` **-nullable:warnings** будет включен контекст предупреждения, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="a9400-115">При указании аргумента `annotations`, **-nullable:annotations**, будет включен контекст с заметками о допустимости значений NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9400-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9400-116">Remarks</span></span>

<span data-ttu-id="a9400-117">Анализ потока используется для определения допустимости значений NULL в переменных в исполняемом коде.</span><span class="sxs-lookup"><span data-stu-id="a9400-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="a9400-118">Выводимая допустимость переменной значения NULL не зависит от объявленной в переменной допустимости значения NULL.</span><span class="sxs-lookup"><span data-stu-id="a9400-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="a9400-119">Вызовы методов анализируются, даже если они условно опущены.</span><span class="sxs-lookup"><span data-stu-id="a9400-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="a9400-120">Например, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="a9400-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="a9400-121">Вызов методов, снабженных следующими атрибутами, также повлияет на анализ потока:</span><span class="sxs-lookup"><span data-stu-id="a9400-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="a9400-122">Простые предварительные условия: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="a9400-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="a9400-123">Простые постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="a9400-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="a9400-124">Условные постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="a9400-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="a9400-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (например, `DoesNotReturnIf(false)` для <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) и <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="a9400-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="a9400-126">Постусловия элемента: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> и <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="a9400-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="a9400-127">Установка данного параметра компилятора в проекте</span><span class="sxs-lookup"><span data-stu-id="a9400-127">To set this compiler option in a project</span></span>

<span data-ttu-id="a9400-128">Измените файл *CSPROJ*, добавив тег `<Nullable>` в иерархию `Project/PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="a9400-128">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="a9400-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a9400-129">See also</span></span>

- [<span data-ttu-id="a9400-130">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="a9400-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a9400-131">Ссылочные типы, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="a9400-131">Nullable reference types</span></span>](../../nullable-references.md)
