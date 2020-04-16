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
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432638"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="91d12-102">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="91d12-102">x:Type Markup Extension</span></span>

<span data-ttu-id="91d12-103">Поставляет объект <xref:System.Type> CLR, который является базовым типом для указанного типа XAML.</span><span class="sxs-lookup"><span data-stu-id="91d12-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="91d12-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="91d12-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="91d12-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="91d12-105">XAML Object Element Usage</span></span>

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a><span data-ttu-id="91d12-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="91d12-106">XAML Values</span></span>

|||
|-|-|
|`prefix`|<span data-ttu-id="91d12-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="91d12-107">Optional.</span></span> <span data-ttu-id="91d12-108">Приставка, на которой отображается непо умолчанию пространство имен XAML.</span><span class="sxs-lookup"><span data-stu-id="91d12-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="91d12-109">Указывать префикс часто не требуется.</span><span class="sxs-lookup"><span data-stu-id="91d12-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="91d12-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="91d12-110">See Remarks.</span></span>|
|`typeNameValue`|<span data-ttu-id="91d12-111">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="91d12-111">Required.</span></span> <span data-ttu-id="91d12-112">Имя типа, разрешимое в текущем пространстве имен XAML по умолчанию; или указанная отображаемые префиксы, если `prefix` поставляется.</span><span class="sxs-lookup"><span data-stu-id="91d12-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|

## <a name="remarks"></a><span data-ttu-id="91d12-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="91d12-113">Remarks</span></span>

<span data-ttu-id="91d12-114">Расширение `x:Type` разметки имеет аналогичную функцию `typeof()` оператора `GetType` в СЗ или оператора в Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="91d12-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>

<span data-ttu-id="91d12-115">Расширение `x:Type` разметки обеспечивает поведение преобразования из строки <xref:System.Type>для свойств, которые принимают тип.</span><span class="sxs-lookup"><span data-stu-id="91d12-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="91d12-116">Ввод — это тип XAML.</span><span class="sxs-lookup"><span data-stu-id="91d12-116">The input is a XAML type.</span></span> <span data-ttu-id="91d12-117">Взаимосвязь между типом ввода XAML <xref:System.Type> и выходом <xref:System.Type> CLR заключается в том, что выходом <xref:System.Xaml.XamlType.UnderlyingType%2A> является входный, <xref:System.Xaml.XamlType>после поиска необходимого <xref:System.Xaml.XamlType> контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> службы, предоставляемой контекстом.</span><span class="sxs-lookup"><span data-stu-id="91d12-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="91d12-118">В службах .NET XAML обработка этого расширения <xref:System.Windows.Markup.TypeExtension> разметки определяется классом.</span><span class="sxs-lookup"><span data-stu-id="91d12-118">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>

<span data-ttu-id="91d12-119">В определенных реализации фреймворка некоторые свойства, которые принимаются <xref:System.Type> в качестве `Name`значения, могут принимать имя типа напрямую (значение строки типа).</span><span class="sxs-lookup"><span data-stu-id="91d12-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="91d12-120">Однако реализация такого поведения является сложным сценарием.</span><span class="sxs-lookup"><span data-stu-id="91d12-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="91d12-121">Например, смотрите нижеследующий раздел "Примечания к использованию WPF".</span><span class="sxs-lookup"><span data-stu-id="91d12-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>

<span data-ttu-id="91d12-122">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="91d12-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="91d12-123">Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>.</span><span class="sxs-lookup"><span data-stu-id="91d12-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="91d12-124">В контексте схемы XAML по умолчанию для .NET XAML Services, основанной на <xref:System.Reflection.MemberInfo.Name%2A> типах CLR, значение <xref:System.Reflection.MemberInfo.Name%2A> этого атрибута является либо желаемым типом, либо содержит, что предшествует префиксу для непо умолчанию отображения пространства имен XAML.</span><span class="sxs-lookup"><span data-stu-id="91d12-124">Under the default XAML schema context for .NET XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>

<span data-ttu-id="91d12-125">Расширение `x:Type` разметки может быть использовано в синтаксисе элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="91d12-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="91d12-126">В этом случае для правильной <xref:System.Windows.Markup.TypeExtension.TypeName%2A> инициализации расширения требуется указание стоимости имущества.</span><span class="sxs-lookup"><span data-stu-id="91d12-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>

<span data-ttu-id="91d12-127">Расширение `x:Type` разметки также может быть использовано в качестве многословного атрибута; однако это использование не является типичным:`<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="91d12-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="91d12-128">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="91d12-128">WPF Usage Notes</span></span>

### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="91d12-129">По умолчанию XAML Namespace и тип овоей картографирования</span><span class="sxs-lookup"><span data-stu-id="91d12-129">Default XAML Namespace and Type Mapping</span></span>

<span data-ttu-id="91d12-130">Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, необходимых для типичных сценариев XAML; поэтому часто можно избежать префиксов при ссылках на значения типа XAML.</span><span class="sxs-lookup"><span data-stu-id="91d12-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="91d12-131">Возможно, вам потребуется сопоставить префикс, если вы ссылаетесь на тип из пользовательской сборки или на типы, которые существуют в сборке WPF, но относятся к пространству имен CLR, которое не было отображено в пространстве имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91d12-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="91d12-132">Для получения дополнительной информации о префиксах, пространствах имен XAML и картографировании названий CLR [см.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)</span><span class="sxs-lookup"><span data-stu-id="91d12-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="91d12-133">Введите свойства, которые поддерживают typename-as-String</span><span class="sxs-lookup"><span data-stu-id="91d12-133">Type Properties That Support Typename-as-String</span></span>

<span data-ttu-id="91d12-134">WPF поддерживает методы, позволяющие указывать <xref:System.Type> значение некоторых свойств типа без необходимости использования расширения `x:Type` разметки.</span><span class="sxs-lookup"><span data-stu-id="91d12-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="91d12-135">Вместо этого можно указать значение в виде строки, которая называет тип.</span><span class="sxs-lookup"><span data-stu-id="91d12-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="91d12-136">Примеры этого <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>и .</span><span class="sxs-lookup"><span data-stu-id="91d12-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="91d12-137">Поддержка такого поведения не обеспечивается ни через конвертеры типа, ни расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="91d12-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="91d12-138">Вместо этого, это поведение отсрочки <xref:System.Windows.FrameworkElementFactory>реализованы через .</span><span class="sxs-lookup"><span data-stu-id="91d12-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>

<span data-ttu-id="91d12-139">Silverlight поддерживает аналогичную конвенцию.</span><span class="sxs-lookup"><span data-stu-id="91d12-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="91d12-140">На самом деле, Silverlight `{x:Type}` в настоящее время не поддерживает `{x:Type}` поддержку языка XAML и не принимает обычаи за пределами нескольких обстоятельств, которые предназначены для поддержки миграции WPF-Silverlight XAML.</span><span class="sxs-lookup"><span data-stu-id="91d12-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="91d12-141">Таким образом, типовое имя как строка поведение встроено во <xref:System.Type> все Silverlight родной оценки собственности, где это значение.</span><span class="sxs-lookup"><span data-stu-id="91d12-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>

## <a name="xaml-2009"></a><span data-ttu-id="91d12-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="91d12-142">XAML 2009</span></span>

<span data-ttu-id="91d12-143">XAML 2009 обеспечивает дополнительную поддержку для генерических типов и изменяет функциональное поведение `x:TypeArguments` и `x:Type` обеспечивает эту поддержку.</span><span class="sxs-lookup"><span data-stu-id="91d12-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>

- <span data-ttu-id="91d12-144">`x:TypeArguments`и связанный элемент объекта для мгновенного общего объекта может быть на элементах, не связанных с корнем.</span><span class="sxs-lookup"><span data-stu-id="91d12-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="91d12-145">Для получения дополнительной информации см. [x:TypeArguments Directive](xtypearguments-directive.md)</span><span class="sxs-lookup"><span data-stu-id="91d12-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

- <span data-ttu-id="91d12-146">XAML 2009 поддерживает синтаксис для указания ограничения общего типа в разметке.</span><span class="sxs-lookup"><span data-stu-id="91d12-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="91d12-147">Это может быть `x:TypeArguments`использовано, , `x:Type`или двумя функциями в сочетании.</span><span class="sxs-lookup"><span data-stu-id="91d12-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>

- <span data-ttu-id="91d12-148">Внедрение WPF XAML при обработке XAML 2009 для загрузки также добавляет эту <xref:System.Type>возможность к неявному поведению преобразования типа для определенных свойств фреймворка, которые используют тип.</span><span class="sxs-lookup"><span data-stu-id="91d12-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>

<span data-ttu-id="91d12-149">В WPF, вы можете использовать функции XAML 2009, но только для свободного XAML (XAML, который не разметка-компилируется).</span><span class="sxs-lookup"><span data-stu-id="91d12-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="91d12-150">Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="91d12-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

## <a name="see-also"></a><span data-ttu-id="91d12-151">См. также</span><span class="sxs-lookup"><span data-stu-id="91d12-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="91d12-152">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="91d12-152">Styling and Templating</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="91d12-153">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="91d12-153">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="91d12-154">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="91d12-154">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
