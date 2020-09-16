---
title: Директива x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544821"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="fc791-102">Директива x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="fc791-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="fc791-103">Изменяет поведение компиляции XAML, если `x:Class` также предоставляется.</span><span class="sxs-lookup"><span data-stu-id="fc791-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="fc791-104">В частности, вместо создания частичного `class` уровня, имеющего `Public` уровень доступа (по умолчанию), предоставленный объект `x:Class` создается с `NotPublic` уровнем доступа.</span><span class="sxs-lookup"><span data-stu-id="fc791-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="fc791-105">Это поведение влияет на уровень доступа для класса в создаваемых сборках.</span><span class="sxs-lookup"><span data-stu-id="fc791-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="fc791-106">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="fc791-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="fc791-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="fc791-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="fc791-108">*нотпублик*</span><span class="sxs-lookup"><span data-stu-id="fc791-108">*NotPublic*</span></span>|<span data-ttu-id="fc791-109">Точная строка, которую необходимо передать в <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> параметре, и зависит от используемого языка программирования кода программной части.</span><span class="sxs-lookup"><span data-stu-id="fc791-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="fc791-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="fc791-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="fc791-111">Зависимости</span><span class="sxs-lookup"><span data-stu-id="fc791-111">Dependencies</span></span>

<span data-ttu-id="fc791-112">[x:Class](xclass-directive.md) также должен быть указан в том же элементе, и этот элемент должен быть корневым элементом на странице.</span><span class="sxs-lookup"><span data-stu-id="fc791-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="fc791-113">Дополнительные сведения см. в [ \[ \] разделе 4.3.1.8 в MS-XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="fc791-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="fc791-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc791-114">Remarks</span></span>

<span data-ttu-id="fc791-115">Значение в параметрах `x:ClassModifier` использования служб XAML .NET зависит от языка программирования.</span><span class="sxs-lookup"><span data-stu-id="fc791-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="fc791-116">Используемая строка зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и какие преобразователи типов он возвращает, чтобы определить значения для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , а также указать, учитывается ли регистр в этом языке.</span><span class="sxs-lookup"><span data-stu-id="fc791-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="fc791-117">Для C# строка, которую необходимо передать для обозначения, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> — `internal` .</span><span class="sxs-lookup"><span data-stu-id="fc791-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="fc791-118">Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> — это `Friend` .</span><span class="sxs-lookup"><span data-stu-id="fc791-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="fc791-119">Для C++/CLI не существует целей, поддерживающих компиляцию XAML; Поэтому значение для передачи не указано.</span><span class="sxs-lookup"><span data-stu-id="fc791-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="fc791-120">Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` в C#, `Public` в Visual Basic), однако указание выполняется редко, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> так как <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc791-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="fc791-121">Другие значения с эквивалентными ограничениями уровня доступа для пользовательского кода, например `private` в C#, не являются значимыми для, `x:ClassModifier` поскольку ссылки на вложенные классы не поддерживаются в XAML, поэтому <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Модификатор имеет тот же результат.</span><span class="sxs-lookup"><span data-stu-id="fc791-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="fc791-122">Примечания по безопасности</span><span class="sxs-lookup"><span data-stu-id="fc791-122">Security Notes</span></span>

<span data-ttu-id="fc791-123">Уровень доступа, объявленный в `x:ClassModifier` , по-прежнему подвергается интерпретации определенными платформами и их возможностями.</span><span class="sxs-lookup"><span data-stu-id="fc791-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="fc791-124">WPF включает возможности для загрузки и создания экземпляров типов `x:ClassModifier` , где имеет значение `internal` , если на этот класс имеется ссылка из ресурса WPF через ссылку на URI типа "Pack".</span><span class="sxs-lookup"><span data-stu-id="fc791-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="fc791-125">Как следствие этого случая и другие, например, реализованные другими платформами, не полагайтесь исключительно на `x:ClassModifier` блокировку всех возможных попыток создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="fc791-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc791-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fc791-126">See also</span></span>

- [<span data-ttu-id="fc791-127">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="fc791-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="fc791-128">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="fc791-128">Code-Behind and XAML in WPF</span></span>](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [<span data-ttu-id="fc791-129">Директива x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="fc791-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="fc791-130">Безопасность (WPF)</span><span class="sxs-lookup"><span data-stu-id="fc791-130">Security (WPF)</span></span>](/dotnet/desktop/wpf/security-wpf)
- [<span data-ttu-id="fc791-131">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="fc791-131">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
