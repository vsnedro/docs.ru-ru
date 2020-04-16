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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433274"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="8f58e-102">Директива x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="8f58e-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="8f58e-103">Изменяет поведение компиляции `x:Class` XAML, когда это также предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="8f58e-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="8f58e-104">В частности, вместо `class` создания `Public` частичного уровня доступа (по умолчанию) при условии `x:Class` создается с уровнем `NotPublic` доступа.</span><span class="sxs-lookup"><span data-stu-id="8f58e-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="8f58e-105">Такое поведение влияет на уровень доступа для класса в сгенерированных сборках.</span><span class="sxs-lookup"><span data-stu-id="8f58e-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="8f58e-106">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="8f58e-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="8f58e-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="8f58e-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="8f58e-108">*Непублично*</span><span class="sxs-lookup"><span data-stu-id="8f58e-108">*NotPublic*</span></span>|<span data-ttu-id="8f58e-109">Точная строка для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> уточнения по сравнению варьируется в зависимости от языка программирования, который используется за кодом.</span><span class="sxs-lookup"><span data-stu-id="8f58e-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="8f58e-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="8f58e-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="8f58e-111">Зависимости</span><span class="sxs-lookup"><span data-stu-id="8f58e-111">Dependencies</span></span>

<span data-ttu-id="8f58e-112">[x: Класс](xclass-directive.md) также должен быть предоставлен на том же элементе, и этот элемент должен быть корневым элементом на странице.</span><span class="sxs-lookup"><span data-stu-id="8f58e-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="8f58e-113">Для получения дополнительной информации [ \[см.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="8f58e-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="8f58e-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f58e-114">Remarks</span></span>

<span data-ttu-id="8f58e-115">Значение `x:ClassModifier` использования услуг .NET XAML варьируется в зависимости от языка программирования.</span><span class="sxs-lookup"><span data-stu-id="8f58e-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="8f58e-116">Строка для использования зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>тип преобразователей он возвращается, чтобы определить значения для и , и является ли этот язык чувствительным к случаю.</span><span class="sxs-lookup"><span data-stu-id="8f58e-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="8f58e-117">Для C, строка, чтобы <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`пройти к назначению .</span><span class="sxs-lookup"><span data-stu-id="8f58e-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="8f58e-118">Для Microsoft Visual Basic .NET строка <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`для передачи в назначенный .</span><span class="sxs-lookup"><span data-stu-id="8f58e-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="8f58e-119">Для КЗ/CLI не существует целевых показателей, поддерживающих компиляцию XAML; таким образом, значение пройти не уточняется.</span><span class="sxs-lookup"><span data-stu-id="8f58e-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="8f58e-120">Вы также <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> можете`public` указать `Public` (в C , в Visual Basic); однако, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> указание выполняется <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> нечасто, поскольку это уже поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8f58e-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="8f58e-121">Другие значения с эквивалентными ограничениями уровня `private` доступа к пользовательскому `x:ClassModifier` коду, например, в C, не имеют значения, поскольку вложенные ссылки класса не поддерживаются в XAML, и, следовательно, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> модификатор имеет тот же эффект.</span><span class="sxs-lookup"><span data-stu-id="8f58e-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="8f58e-122">Примечания по безопасности</span><span class="sxs-lookup"><span data-stu-id="8f58e-122">Security Notes</span></span>

<span data-ttu-id="8f58e-123">Заявленный уровень `x:ClassModifier` доступа по-прежнему регулируется конкретными рамками и их возможностями.</span><span class="sxs-lookup"><span data-stu-id="8f58e-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="8f58e-124">WPF включает в себя возможности для `x:ClassModifier` `internal`загрузки и мгновенного типов, где есть, если этот класс ссылается с ресурса WPF через ссылку пакета URI.</span><span class="sxs-lookup"><span data-stu-id="8f58e-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="8f58e-125">Как следствие этого случая и потенциально другие, как он реализован другими рамками, не полагаться исключительно на `x:ClassModifier` блокировать все возможные попытки мгновенного.</span><span class="sxs-lookup"><span data-stu-id="8f58e-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f58e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8f58e-126">See also</span></span>

- [<span data-ttu-id="8f58e-127">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="8f58e-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="8f58e-128">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="8f58e-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="8f58e-129">Директива x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="8f58e-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="8f58e-130">Безопасность (WPF)</span><span class="sxs-lookup"><span data-stu-id="8f58e-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="8f58e-131">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="8f58e-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
