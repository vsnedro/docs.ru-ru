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
ms.openlocfilehash: b812939cbaa74576361de534c0d39ba45536cbcf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555176"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="b5589-102">Расширение разметки x:Array</span><span class="sxs-lookup"><span data-stu-id="b5589-102">x:Array Markup Extension</span></span>

<span data-ttu-id="b5589-103">Предоставляет общую поддержку для массивов объектов в XAML с помощью расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="b5589-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="b5589-104">Это соответствует `x:ArrayExtension` типу XAML в [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="b5589-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b5589-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="b5589-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="b5589-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="b5589-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="b5589-107">Имя типа, который `x:Array` будет содержать.</span><span class="sxs-lookup"><span data-stu-id="b5589-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="b5589-108">`typeName` может быть (и часто) префиксом для пространства имен XAML, содержащего определения типов XAML.</span><span class="sxs-lookup"><span data-stu-id="b5589-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="b5589-109">Содержимое элементов, назначенное встроенному `ArrayExtension.Items` свойству.</span><span class="sxs-lookup"><span data-stu-id="b5589-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="b5589-110">Как правило, эти элементы указываются как один или несколько объектных элементов, содержащихся в `x:Array` открывающих и закрывающих тегах.</span><span class="sxs-lookup"><span data-stu-id="b5589-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="b5589-111">Указанные здесь объекты должны быть назначены типу XAML, указанному в `typeName` .</span><span class="sxs-lookup"><span data-stu-id="b5589-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b5589-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5589-112">Remarks</span></span>

<span data-ttu-id="b5589-113">`Type` является обязательным атрибутом для всех `x:Array` объектных элементов.</span><span class="sxs-lookup"><span data-stu-id="b5589-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="b5589-114">`Type`Значение параметра не обязательно должно использовать `x:Type` расширение разметки; короткое имя типа — это тип XAML, который может быть указан в виде строки.</span><span class="sxs-lookup"><span data-stu-id="b5589-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="b5589-115">В реализации служб XAML .NET отношение между входным типом XAML и выходными данными CLR <xref:System.Type> созданного массива зависит от контекста службы для расширений разметки.</span><span class="sxs-lookup"><span data-stu-id="b5589-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="b5589-116">Выходные данные <xref:System.Type> — это <xref:System.Xaml.XamlType.UnderlyingType%2A> Тип входного типа XAML после поиска необходимых данных на <xref:System.Xaml.XamlType> основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> службы, предоставляемой контекстом.</span><span class="sxs-lookup"><span data-stu-id="b5589-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="b5589-117">При обработке содержимое массива назначается `ArrayExtension.Items` внутреннему свойству.</span><span class="sxs-lookup"><span data-stu-id="b5589-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="b5589-118">В <xref:System.Windows.Markup.ArrayExtension> реализации это представлено <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b5589-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b5589-119">В реализации служб XAML .NET обработка этого расширения разметки определяется <xref:System.Windows.Markup.ArrayExtension> классом.</span><span class="sxs-lookup"><span data-stu-id="b5589-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="b5589-120"><xref:System.Windows.Markup.ArrayExtension> не запечатан, и его можно использовать в качестве основания для реализации расширения разметки для пользовательского типа массива.</span><span class="sxs-lookup"><span data-stu-id="b5589-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="b5589-121">`x:Array` более предназначен для общего расширения языка в XAML.</span><span class="sxs-lookup"><span data-stu-id="b5589-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="b5589-122">Но `x:Array` также может быть полезен для указания значений XAML определенных свойств, которые принимают коллекции, ПОДДЕРЖИВАЕМЫЕ XAML, в качестве содержимого структурированных свойств.</span><span class="sxs-lookup"><span data-stu-id="b5589-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="b5589-123">Например, можно указать содержимое <xref:System.Collections.IEnumerable> свойства с использованием `x:Array` .</span><span class="sxs-lookup"><span data-stu-id="b5589-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="b5589-124">`x:Array` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="b5589-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="b5589-125">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="b5589-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="b5589-126">`x:Array` является частично исключением из этого правила, так как не предоставляет альтернативную обработку значения атрибута, `x:Array` предоставляет альтернативную обработку внутреннего текстового содержимого.</span><span class="sxs-lookup"><span data-stu-id="b5589-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="b5589-127">Это поведение позволяет использовать типы, которые могут не поддерживаться существующей моделью содержимого, для группирования в массив и ссылки на них в коде программной части путем доступа к именованному массиву. <xref:System.Array> для получения отдельных элементов массива можно вызывать методы.</span><span class="sxs-lookup"><span data-stu-id="b5589-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="b5589-128">Все расширения разметки в XAML используют фигурные скобки ( {,} `)` в синтаксисе атрибутов, который является соглашением, по которому обработчик XAML распознает, что расширение разметки должно обрабатывать значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="b5589-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="b5589-129">Дополнительные сведения о расширениях разметки в целом см. в разделе [преобразователи типов и расширения разметки для XAML](type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="b5589-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="b5589-130">В XAML 2009 `x:Array` определяется как примитив языка вместо расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="b5589-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="b5589-131">Дополнительные сведения см. [в разделе Встроенные типы для общих примитивов языка XAML](types-for-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="b5589-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="b5589-132">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="b5589-132">WPF Usage Notes</span></span>

<span data-ttu-id="b5589-133">Как правило, элементы объекта, заполняющие элемент, `x:Array` не являются элементами, которые существуют в [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] пространстве имен XAML, и для них требуется сопоставление префикса с пространством имен XAML, отличным от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5589-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="b5589-134">Например, ниже приведен простой массив из двух строк с `sys` префиксом (а также `x` ), определенным на уровне массива.</span><span class="sxs-lookup"><span data-stu-id="b5589-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="b5589-135">Для пользовательских типов, которые используются в качестве элементов массива, класс также должен поддерживать требования для создания экземпляров в XAML в виде объектных элементов.</span><span class="sxs-lookup"><span data-stu-id="b5589-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="b5589-136">Дополнительные сведения см. в разделе [XAML и пользовательские классы для WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span><span class="sxs-lookup"><span data-stu-id="b5589-136">For more information, see [XAML and Custom Classes for WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5589-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b5589-137">See also</span></span>

- [<span data-ttu-id="b5589-138">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="b5589-138">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [<span data-ttu-id="b5589-139">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="b5589-139">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
