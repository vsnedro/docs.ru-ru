---
title: Расширение разметки x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433268"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="d7dc4-102">Расширение разметки x:Static</span><span class="sxs-lookup"><span data-stu-id="d7dc4-102">x:Static Markup Extension</span></span>

<span data-ttu-id="d7dc4-103">Ссылки на любую статическую сущность кода по стоимости, которая определяется в общей языковой спецификации (CLS) - совместимой с</span><span class="sxs-lookup"><span data-stu-id="d7dc4-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="d7dc4-104">Наносимое статическое свойство может быть использовано для обеспечения значения свойства в XAML.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="d7dc4-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="d7dc4-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="d7dc4-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="d7dc4-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="d7dc4-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-107">Optional.</span></span> <span data-ttu-id="d7dc4-108">Префикс, отображаемый к отображенное, не по умолчанию XAML пространство имени.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="d7dc4-109">`prefix`отображается явно в использовании, потому что вы редко ссылаетесь на статические свойства, которые приходят из пространства имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="d7dc4-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="d7dc4-111">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-111">Required.</span></span> <span data-ttu-id="d7dc4-112">Имя типа, определяющего желаемый статический член.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="d7dc4-113">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-113">Required.</span></span> <span data-ttu-id="d7dc4-114">Имя желаемого элемента статического значения (константа, статическое свойство, поле или значение перечисления).</span><span class="sxs-lookup"><span data-stu-id="d7dc4-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="d7dc4-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7dc4-115">Remarks</span></span>

<span data-ttu-id="d7dc4-116">На ссылку — кодовое образование должно быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="d7dc4-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="d7dc4-117">Константа</span><span class="sxs-lookup"><span data-stu-id="d7dc4-117">A constant</span></span>
- <span data-ttu-id="d7dc4-118">Статическое свойство</span><span class="sxs-lookup"><span data-stu-id="d7dc4-118">A static property</span></span>
- <span data-ttu-id="d7dc4-119">Поле</span><span class="sxs-lookup"><span data-stu-id="d7dc4-119">A field</span></span>
- <span data-ttu-id="d7dc4-120">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="d7dc4-120">An enumeration value</span></span>

<span data-ttu-id="d7dc4-121">Указание любой другой сущности кода, например нестатического свойства, вызывает ошибку времени компиляции, если компилируется разметка XAML, или исключение для разбора времени загрузки XAML.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="d7dc4-122">Можно сделать `x:Static` ссылки на статические поля или свойства, которые не находятся в пространстве имен XAML по умолчанию для текущего документа XAML; однако для этого требуется отображение приставки.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="d7dc4-123">Пространства имен XAML почти всегда определяются на корневом элементе документа XAML.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="d7dc4-124">Операции поиска статических свойств могут выполняться службами .NET XAML и его читателями XAML и авторами XAML, когда они работают с контекстом схемы XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="d7dc4-125">В этом контексте схемы XAML можно использовать отражение CLR для обеспечения необходимых статических значений для построения графика объекта.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="d7dc4-126">Вы `typeName` указываете на самом деле имя типа XAML, а не имя типа CLR, хотя они по существу одно и то же имя при использовании контекста схемы XAML по умолчанию или при использовании всех существующих CLR-платформ XAML-реализации.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="d7dc4-127">Используйте осторожность, `x:Static` когда вы делаете ссылки, которые не являются непосредственно тип свойства стоимости.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="d7dc4-128">В последовательности обработки XAML при условии, что значения расширения разметки не вызывают дополнительного преобразования значений.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="d7dc4-129">Это верно даже `x:Static` в том случае, если ссылка создает строку текста, а преобразование значений для значений атрибутов, основанных на строке текста, обычно происходит либо для конкретного участника, либо для любых значений типа возврата.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="d7dc4-130">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="d7dc4-131">Строковая лексема, указываемая после строки идентификатора `x:Static`, присваивается в качестве значения <xref:System.Windows.Markup.StaticExtension.Member%2A> соответствующего класса расширения <xref:System.Windows.Markup.StaticExtension>.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="d7dc4-132">Есть два других использования XAML, которые технически возможны.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="d7dc4-133">Тем не менее, эти обычаи встречаются реже, потому что они излишне многословны:</span><span class="sxs-lookup"><span data-stu-id="d7dc4-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="d7dc4-134">Синтаксис элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="d7dc4-135">Атрибут синтаксиса с явным свойством участника для строки инициализации.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="d7dc4-136">В реализации .NET XAML Services обработка этого расширения <xref:System.Windows.Markup.StaticExtension> разметки определяется классом.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="d7dc4-137">`x:Static` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="d7dc4-138">Все расширения разметки в `{` XAML используют и `}` символы в их синтаксисе атрибутов, который является конвенцией, по которой процессор XAML признает, что расширение разметки должно обеспечить значение.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="d7dc4-139">Дополнительные сведения о расширениях разметки см. в разделе [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc4-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="d7dc4-140">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="d7dc4-140">WPF Usage Notes</span></span>

<span data-ttu-id="d7dc4-141">Пространство имен XAML, используемее по умолчанию для программирования WPF, не содержит многих полезных статических свойств, `{x:Static}` и большинство полезных статических свойств имеют поддержку, такую как преобразователи типов, которые облегчают использование, не требуя.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="d7dc4-142">Для статических свойств необходимо сопоставить префикс для пространства имен XAML, если одно из следующих свойств верно:</span><span class="sxs-lookup"><span data-stu-id="d7dc4-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="d7dc4-143">Вы ссылаетесь на тип, который существует в WPF, но не является частью`http://schemas.microsoft.com/winfx/2006/xaml/presentation`пространства имен XAML по умолчанию для WPF ().</span><span class="sxs-lookup"><span data-stu-id="d7dc4-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="d7dc4-144">Это довольно распространенный сценарий для использования `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="d7dc4-145">Например, можно использовать `x:Static` ссылку с отображением <xref:System> пространства имен XAML на пространство имен CLR и <xref:System.Environment> сборку mscorlib, чтобы ссылаться на статические свойства класса.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="d7dc4-146">Вы ссылаетесь на тип из пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="d7dc4-147">Вы ссылаетесь на тип, который существует в сборке WPF, но этот тип находится в пространстве имен CLR, которое не было отображено, чтобы быть частью пространства имен WPF по умолчанию XAML.</span><span class="sxs-lookup"><span data-stu-id="d7dc4-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="d7dc4-148">Отображение пространства имен CLR в пространстве имен XAML по умолчанию для WPF выполняется по определениям в различных сборках WPF (для получения дополнительной информации об этой концепции см. [XAML Namespaces и Namespace Mapping для WPF XAML).](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)</span><span class="sxs-lookup"><span data-stu-id="d7dc4-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="d7dc4-149">Некартные пространства имен CLR могут существовать, если это пространство имен CLR состоит в основном из <xref:System.Windows.Threading>определений классов, которые обычно не предназначены для XAML, таких как .</span><span class="sxs-lookup"><span data-stu-id="d7dc4-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="d7dc4-150">Для получения дополнительной информации о том, как использовать префиксы и пространства имен XAML для WPF, [см.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)</span><span class="sxs-lookup"><span data-stu-id="d7dc4-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7dc4-151">См. также</span><span class="sxs-lookup"><span data-stu-id="d7dc4-151">See also</span></span>

- [<span data-ttu-id="d7dc4-152">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="d7dc4-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="d7dc4-153">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="d7dc4-153">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
