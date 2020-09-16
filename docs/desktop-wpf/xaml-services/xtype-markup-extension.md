---
title: Расширение разметки x:Type
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: 00e6684f6ad1eb8d96f72f49bd5e0d211c8166c3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559074"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="46c3a-102">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="46c3a-102">x:Type Markup Extension</span></span>

<span data-ttu-id="46c3a-103">Предоставляет объект CLR <xref:System.Type> , который является базовым типом для указанного типа XAML.</span><span class="sxs-lookup"><span data-stu-id="46c3a-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="46c3a-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="46c3a-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="46c3a-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="46c3a-105">XAML Object Element Usage</span></span>

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a><span data-ttu-id="46c3a-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="46c3a-106">XAML Values</span></span>

|||
|-|-|
|`prefix`|<span data-ttu-id="46c3a-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46c3a-107">Optional.</span></span> <span data-ttu-id="46c3a-108">Префикс, который сопоставляет пространство имен XAML, отличное от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46c3a-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="46c3a-109">Указывать префикс часто необязательно.</span><span class="sxs-lookup"><span data-stu-id="46c3a-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="46c3a-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="46c3a-110">See Remarks.</span></span>|
|`typeNameValue`|<span data-ttu-id="46c3a-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="46c3a-111">Required.</span></span> <span data-ttu-id="46c3a-112">Имя типа, которое разрешается в текущее пространство имен XAML по умолчанию; или указанный сопоставленный префикс, если указан `prefix` аргумент.</span><span class="sxs-lookup"><span data-stu-id="46c3a-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|

## <a name="remarks"></a><span data-ttu-id="46c3a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="46c3a-113">Remarks</span></span>

<span data-ttu-id="46c3a-114">`x:Type`Расширение разметки имеет аналогичную функцию `typeof()` оператору в C# или `GetType` операторе в Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46c3a-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>

<span data-ttu-id="46c3a-115">`x:Type`Расширение разметки предоставляет поведение преобразования из строки для свойств, которые принимают тип <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="46c3a-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="46c3a-116">Входные данные являются типом XAML.</span><span class="sxs-lookup"><span data-stu-id="46c3a-116">The input is a XAML type.</span></span> <span data-ttu-id="46c3a-117">Связь между входным типом XAML и выходным CLR заключается в том <xref:System.Type> , что выходные данные <xref:System.Type> являются <xref:System.Xaml.XamlType.UnderlyingType%2A> входными данными <xref:System.Xaml.XamlType> после поиска необходимых данных на <xref:System.Xaml.XamlType> основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> службы, предоставляемой контекстом.</span><span class="sxs-lookup"><span data-stu-id="46c3a-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="46c3a-118">В службах .NET XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.TypeExtension> классом.</span><span class="sxs-lookup"><span data-stu-id="46c3a-118">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>

<span data-ttu-id="46c3a-119">В определенных реализациях платформы некоторые свойства, принимающие в <xref:System.Type> качестве значения, могут принимать имя типа напрямую (строковое значение типа `Name` ).</span><span class="sxs-lookup"><span data-stu-id="46c3a-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="46c3a-120">Однако реализация этого поведения является сложным сценарием.</span><span class="sxs-lookup"><span data-stu-id="46c3a-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="46c3a-121">Примеры см. в разделе "Примечания об использовании WPF" ниже.</span><span class="sxs-lookup"><span data-stu-id="46c3a-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>

<span data-ttu-id="46c3a-122">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="46c3a-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="46c3a-123">Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>.</span><span class="sxs-lookup"><span data-stu-id="46c3a-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="46c3a-124">В контексте схемы XAML по умолчанию для служб XAML .NET, основанных на типах CLR, значение этого атрибута является либо либо <xref:System.Reflection.MemberInfo.Name%2A> типом требуемого типа, либо содержит <xref:System.Reflection.MemberInfo.Name%2A> префикс для сопоставления пространства имен XAML, не являющегося по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46c3a-124">Under the default XAML schema context for .NET XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>

<span data-ttu-id="46c3a-125">`x:Type`Расширение разметки можно использовать в синтаксисе объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="46c3a-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="46c3a-126">В этом случае <xref:System.Windows.Markup.TypeExtension.TypeName%2A> для правильной инициализации расширения требуется указать значение свойства.</span><span class="sxs-lookup"><span data-stu-id="46c3a-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>

<span data-ttu-id="46c3a-127">`x:Type`Расширение разметки также можно использовать в качестве подробного атрибута, однако это не является типичным.`<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="46c3a-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="46c3a-128">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="46c3a-128">WPF Usage Notes</span></span>

### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="46c3a-129">Сопоставление типов и пространства имен XAML по умолчанию</span><span class="sxs-lookup"><span data-stu-id="46c3a-129">Default XAML Namespace and Type Mapping</span></span>

<span data-ttu-id="46c3a-130">Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, необходимых для типичных сценариев XAML. Таким образом, часто можно избежать префиксов при ссылке на значения типа XAML.</span><span class="sxs-lookup"><span data-stu-id="46c3a-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="46c3a-131">Может потребоваться сопоставить префикс, если вы ссылаетесь на тип из пользовательской сборки или для типов, существующих в сборке WPF, но из пространства имен CLR, которое не было сопоставлено с пространством имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46c3a-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="46c3a-132">Дополнительные сведения о префиксах, пространствах имен XAML и сопоставлении пространств имен CLR см. в разделе [пространства имен и сопоставление пространств имен XAML для WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).</span><span class="sxs-lookup"><span data-stu-id="46c3a-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).</span></span>

### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="46c3a-133">Свойства типа, поддерживающие TypeName в виде строки</span><span class="sxs-lookup"><span data-stu-id="46c3a-133">Type Properties That Support Typename-as-String</span></span>

<span data-ttu-id="46c3a-134">WPF поддерживает приемы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без `x:Type` использования расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="46c3a-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="46c3a-135">Вместо этого можно указать значение в виде строки с именем типа.</span><span class="sxs-lookup"><span data-stu-id="46c3a-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="46c3a-136">Примеры: <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> и <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="46c3a-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46c3a-137">Поддержка этого поведения не предоставляется ни с помощью преобразователей типов, ни из расширений разметки.</span><span class="sxs-lookup"><span data-stu-id="46c3a-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="46c3a-138">Вместо этого это поведение, реализованное с помощью <xref:System.Windows.FrameworkElementFactory> .</span><span class="sxs-lookup"><span data-stu-id="46c3a-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>

<span data-ttu-id="46c3a-139">Silverlight поддерживает аналогичное соглашение.</span><span class="sxs-lookup"><span data-stu-id="46c3a-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="46c3a-140">На самом деле Silverlight в настоящее время не поддерживает `{x:Type}` поддержку языка XAML и не принимает `{x:Type}` использование за пределами нескольких обстоятельств, предназначенных для поддержки миграции XAML WPF-Silverlight.</span><span class="sxs-lookup"><span data-stu-id="46c3a-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="46c3a-141">Таким образом, поведение типа "имя-строка" встроено во все вычисления собственного свойства Silverlight, где <xref:System.Type> — это значение.</span><span class="sxs-lookup"><span data-stu-id="46c3a-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>

## <a name="xaml-2009"></a><span data-ttu-id="46c3a-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="46c3a-142">XAML 2009</span></span>

<span data-ttu-id="46c3a-143">XAML 2009 обеспечивает дополнительную поддержку для универсальных типов и изменяет поведение функций `x:TypeArguments` и `x:Type` для предоставления этой поддержки.</span><span class="sxs-lookup"><span data-stu-id="46c3a-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>

- <span data-ttu-id="46c3a-144">`x:TypeArguments` и связанный элемент объекта для создания экземпляра универсального объекта может находиться в элементах, отличных от корневого.</span><span class="sxs-lookup"><span data-stu-id="46c3a-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="46c3a-145">Дополнительные сведения см. в разделе "XAML 2009" [директивы x:TypeArguments](xtypearguments-directive.md).</span><span class="sxs-lookup"><span data-stu-id="46c3a-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

- <span data-ttu-id="46c3a-146">XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметке.</span><span class="sxs-lookup"><span data-stu-id="46c3a-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="46c3a-147">Это можно использовать `x:TypeArguments` в, by `x:Type` или двух функциях в сочетании.</span><span class="sxs-lookup"><span data-stu-id="46c3a-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>

- <span data-ttu-id="46c3a-148">Реализация XAML в WPF при обработке XAML 2009 для загрузки также добавляет эту возможность в поведение неявного преобразования типов для определенных свойств платформы, использующих тип <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="46c3a-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>

<span data-ttu-id="46c3a-149">В WPF можно использовать функции XAML 2009, но только для свободного XAML (XAML, не компилируемого разметкой).</span><span class="sxs-lookup"><span data-stu-id="46c3a-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="46c3a-150">Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="46c3a-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

## <a name="see-also"></a><span data-ttu-id="46c3a-151">См. также</span><span class="sxs-lookup"><span data-stu-id="46c3a-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="46c3a-152">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="46c3a-152">Styling and Templating</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="46c3a-153">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="46c3a-153">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="46c3a-154">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="46c3a-154">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
