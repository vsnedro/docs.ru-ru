---
title: Расширение разметки x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433286"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="8296b-102">Расширение разметки x:Array</span><span class="sxs-lookup"><span data-stu-id="8296b-102">x:Array Markup Extension</span></span>

<span data-ttu-id="8296b-103">Обеспечивает общую поддержку массивов объектов в XAML через расширение разметки.</span><span class="sxs-lookup"><span data-stu-id="8296b-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="8296b-104">Это соответствует типу `x:ArrayExtension` XAML в «MS-XAML».</span><span class="sxs-lookup"><span data-stu-id="8296b-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="8296b-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="8296b-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="8296b-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="8296b-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="8296b-107">Имя типа, который `x:Array` будет содержать ваш.</span><span class="sxs-lookup"><span data-stu-id="8296b-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="8296b-108">`typeName`может быть (и часто) префиксируется для пространства имен XAML, содержащего определения типа XAML.</span><span class="sxs-lookup"><span data-stu-id="8296b-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="8296b-109">Содержимое элементов, присвоенное свойству. `ArrayExtension.Items`</span><span class="sxs-lookup"><span data-stu-id="8296b-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="8296b-110">Как правило, эти элементы определяются как `x:Array` один или несколько элементов объекта, содержащиеся в тегах открытия и закрытия.</span><span class="sxs-lookup"><span data-stu-id="8296b-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="8296b-111">Объекты, указанные здесь, как ожидается, будут `typeName`присваиваться типу XAML, указанному в .</span><span class="sxs-lookup"><span data-stu-id="8296b-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8296b-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8296b-112">Remarks</span></span>

<span data-ttu-id="8296b-113">`Type`является необходимым атрибутом `x:Array` для всех элементов объекта.</span><span class="sxs-lookup"><span data-stu-id="8296b-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="8296b-114">Значение `Type` параметра не требуется `x:Type` для использования расширения разметки; коротким названием типа является тип XAML, который может быть указан как строка.</span><span class="sxs-lookup"><span data-stu-id="8296b-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="8296b-115">В реализации .NET XAML Services взаимосвязь между входним типом XAML и выходным CLR <xref:System.Type> созданного массива зависит от контекста службы для расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="8296b-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="8296b-116">Выход <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> это тип ввода XAML, после <xref:System.Xaml.XamlType> поиска необходимого контекста схемы <xref:System.Windows.Markup.IXamlTypeResolver> XAML и службы, предоставляемой контекстом.</span><span class="sxs-lookup"><span data-stu-id="8296b-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="8296b-117">При обработке содержимое массива `ArrayExtension.Items` присваивается свойству.</span><span class="sxs-lookup"><span data-stu-id="8296b-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="8296b-118">В <xref:System.Windows.Markup.ArrayExtension> реализации это представлено <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8296b-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="8296b-119">В реализации .NET XAML Services обработка этого расширения <xref:System.Windows.Markup.ArrayExtension> разметки определяется классом.</span><span class="sxs-lookup"><span data-stu-id="8296b-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="8296b-120"><xref:System.Windows.Markup.ArrayExtension>не запечатан и может быть использован в качестве основы для реализации расширения разметки для пользовательского типа массива.</span><span class="sxs-lookup"><span data-stu-id="8296b-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="8296b-121">`x:Array`больше предназначендля для общей расширяемости языка в XAML.</span><span class="sxs-lookup"><span data-stu-id="8296b-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="8296b-122">Но `x:Array` также может быть полезно для указания значений XAML определенных свойств, которые принимают XAML-поддерживаемые коллекции в качестве структурированного содержимого свойства.</span><span class="sxs-lookup"><span data-stu-id="8296b-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="8296b-123">Например, можно указать содержимое <xref:System.Collections.IEnumerable> свойства `x:Array` с использованием.</span><span class="sxs-lookup"><span data-stu-id="8296b-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="8296b-124">`x:Array` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="8296b-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="8296b-125">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="8296b-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="8296b-126">`x:Array`частично является исключением из этого правила, поскольку `x:Array` вместо альтернативной обработки значений атрибутов предусмотрена альтернативная обработка содержимого внутреннего текста.</span><span class="sxs-lookup"><span data-stu-id="8296b-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="8296b-127">Такое поведение позволяет группам типов, которые не могут быть поддержаны существующей моделью содержимого, быть сгруппированы в массив и упомянутые позднее в коде позади, приодя к названному массиву; вы можете <xref:System.Array> вызвать методы, чтобы получить отдельные элементы массива.</span><span class="sxs-lookup"><span data-stu-id="8296b-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="8296b-128">Все расширения разметки в XAML{,} `)` используют скобки (в их синтаксисе атрибута, который является конвенцией, по которой процессор XAML признает, что расширение разметки должно обрабатывать значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="8296b-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="8296b-129">Для получения дополнительной информации о расширениях разметки в целом [см.](type-converters-and-markup-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="8296b-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="8296b-130">В XAML 2009, `x:Array` определяется как язык примитивный вместо расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="8296b-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="8296b-131">Для получения дополнительной [Built-in Types for Common XAML Language Primitives](types-for-primitives.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="8296b-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="8296b-132">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="8296b-132">WPF Usage Notes</span></span>

<span data-ttu-id="8296b-133">Как правило, `x:Array` элементы объекта, которые населяют, не являются элементами, которые существуют в пространстве имен [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML, и требуют отображения приставки к непо умолчанию XAML namespace.</span><span class="sxs-lookup"><span data-stu-id="8296b-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="8296b-134">Например, ниже приводится простой массив из `sys` двух строк, `x`с приставкой (а также) определенным на уровне массива.</span><span class="sxs-lookup"><span data-stu-id="8296b-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="8296b-135">Для пользовательских типов, которые используются в качестве элементов массива, класс должен также поддерживать требования к мгновенному использованию в XAML в качестве элементов объекта.</span><span class="sxs-lookup"><span data-stu-id="8296b-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="8296b-136">Для получения дополнительной [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="8296b-136">For more information, see [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8296b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8296b-137">See also</span></span>

- [<span data-ttu-id="8296b-138">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="8296b-138">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="8296b-139">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="8296b-139">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
