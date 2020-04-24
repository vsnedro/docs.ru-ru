---
title: Преобразователи типов или расширения разметки для XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services
- XAML [XAML Services], value converters
- XAML [XAML Services], markup extension services
- value converters for XAML [XAML Services]
- XAML [XAML Services], service context
ms.assetid: db07a952-05ce-4aa4-b6f9-aac7397d0326
ms.openlocfilehash: bee94b03d4fd6e6f5ef8571e83f554b381dd6582
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432890"
---
# <a name="type-converters-and-markup-extensions-for-xaml"></a><span data-ttu-id="75ca7-102">Преобразователи типов или расширения разметки для XAML</span><span class="sxs-lookup"><span data-stu-id="75ca7-102">Type Converters and Markup Extensions for XAML</span></span>

<span data-ttu-id="75ca7-103">Преобразователи типов и расширения разметки — это два метода, используемых системами типов XAML и средствами записи XAML для создания компонентов графа объектов.</span><span class="sxs-lookup"><span data-stu-id="75ca7-103">Type converters and markup extensions are two techniques that XAML type systems and XAML writers use to generate object graph components.</span></span> <span data-ttu-id="75ca7-104">Хотя они обладают общими характеристиками, преобразователи типов и расширения разметки представляются по-разному в потоке узлов XAML.</span><span class="sxs-lookup"><span data-stu-id="75ca7-104">Although they share some characteristics, type converters and markup extensions are represented differently in a XAML node stream.</span></span> <span data-ttu-id="75ca7-105">В этой документации преобразователи типов, расширения разметки и аналогичные конструкции иногда называются преобразователями значений.</span><span class="sxs-lookup"><span data-stu-id="75ca7-105">In this documentation set, type converters, markup extensions, and similar constructs are sometimes collectively referred to as value converters.</span></span>

## <a name="value-converters"></a><span data-ttu-id="75ca7-106">Преобразователи значений</span><span class="sxs-lookup"><span data-stu-id="75ca7-106">Value Converters</span></span>

<span data-ttu-id="75ca7-107">В XAML преобразователи значений используются для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="75ca7-107">In XAML, value converters are used for various scenarios.</span></span> <span data-ttu-id="75ca7-108">Ниже перечислены различные типы преобразователей значений в XAML.</span><span class="sxs-lookup"><span data-stu-id="75ca7-108">The following list shows the different types of value converters in XAML:</span></span>

- <span data-ttu-id="75ca7-109">Преобразователь типов</span><span class="sxs-lookup"><span data-stu-id="75ca7-109">Type converter</span></span>

- <span data-ttu-id="75ca7-110">Расширение разметки</span><span class="sxs-lookup"><span data-stu-id="75ca7-110">Markup extension</span></span>

- <span data-ttu-id="75ca7-111">Сериализатор значений</span><span class="sxs-lookup"><span data-stu-id="75ca7-111">Value serializer</span></span>

- <span data-ttu-id="75ca7-112">Связанный класс или вспомогательный класс, предоставляющий логику для текстового синтаксиса XAML.</span><span class="sxs-lookup"><span data-stu-id="75ca7-112">Related class or support class that provides the logic for a XAML text syntax</span></span>

## <a name="type-converters"></a><span data-ttu-id="75ca7-113">Преобразователи типов</span><span class="sxs-lookup"><span data-stu-id="75ca7-113">Type Converters</span></span>

<span data-ttu-id="75ca7-114">В определении .NET XAML Services преобразователи <xref:System.ComponentModel.TypeConverter> типов представляют классы, вытекающие из класса CLR.</span><span class="sxs-lookup"><span data-stu-id="75ca7-114">In .NET XAML Services definition, type converters are classes that derive from the CLR <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="75ca7-115"><xref:System.ComponentModel.TypeConverter>это класс, который был в .NET до существования XAML.</span><span class="sxs-lookup"><span data-stu-id="75ca7-115"><xref:System.ComponentModel.TypeConverter> is a class that was in the .NET before XAML existed.</span></span> <span data-ttu-id="75ca7-116">Его первоначальная цель заключалась в поддержке окон свойств и аналогичных текстовых метафор редактирования свойств IDE.</span><span class="sxs-lookup"><span data-stu-id="75ca7-116">Its original purpose was to support property windows and similar text-based editing metaphors for IDE properties.</span></span> <span data-ttu-id="75ca7-117">Введение XAML в .NET <xref:System.ComponentModel.TypeConverter> используется для преобразования синтаксиса текста (как это содержится в значении атрибута или узло значения XAML) в объект.</span><span class="sxs-lookup"><span data-stu-id="75ca7-117">The introduction of XAML to .NET uses <xref:System.ComponentModel.TypeConverter> to convert a text syntax (as found in an attribute value or a XAML value node) into an object.</span></span> <span data-ttu-id="75ca7-118"><xref:System.ComponentModel.TypeConverter> может также использоваться для сериализации значения объекта в текстовый синтаксис.</span><span class="sxs-lookup"><span data-stu-id="75ca7-118"><xref:System.ComponentModel.TypeConverter> can also be used to serialize an object value to text syntax.</span></span> <span data-ttu-id="75ca7-119"><xref:System.ComponentModel.TypeConverter>также использовался в предыдущих реализациях XAML, специфичных для конкретных рамок, в Windows Presentation Foundation (WPF) и Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="75ca7-119"><xref:System.ComponentModel.TypeConverter> was also used in previous framework-specific XAML implementations in Windows Presentation Foundation (WPF) and Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="75ca7-120">Дополнительные сведения о <xref:System.ComponentModel.TypeConverter> в XAML см. в разделе [Type Converters for XAML Overview](type-converters-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75ca7-120">For more information about the <xref:System.ComponentModel.TypeConverter> in XAML, see [Type Converters for XAML Overview](type-converters-overview.md).</span></span>

## <a name="markup-extensions"></a><span data-ttu-id="75ca7-121">Расширения разметки</span><span class="sxs-lookup"><span data-stu-id="75ca7-121">Markup Extensions</span></span>

<span data-ttu-id="75ca7-122">В реализации .NET XAML Services расширения разметки — это классы, вытекающие <xref:System.Windows.Markup.MarkupExtension> из класса.</span><span class="sxs-lookup"><span data-stu-id="75ca7-122">In .NET XAML Services implementation, markup extensions are classes that derive from the <xref:System.Windows.Markup.MarkupExtension> class.</span></span> <span data-ttu-id="75ca7-123">Расширения разметки — это понятие, которое возникло в языке XAML.</span><span class="sxs-lookup"><span data-stu-id="75ca7-123">Markup extensions are a concept that in this form is originated by the XAML language.</span></span> <span data-ttu-id="75ca7-124">Расширение разметки можно представить чем-то вроде расширяемой Escape-последовательности, вызывающей класс службы для реализации своей логики.</span><span class="sxs-lookup"><span data-stu-id="75ca7-124">You can think of a markup extension as being something like an extensible escape sequence that calls into a service class to provide its logic.</span></span> <span data-ttu-id="75ca7-125">С точки зрения разметки обработчики XAML всегда распознают расширение разметки как текстовую последовательность, начинающуюся с открывающей фигурной скобки ({}) в текстовой строке.</span><span class="sxs-lookup"><span data-stu-id="75ca7-125">In terms of markup, XAML processors universally recognize a markup extension by a text sequence that starts with an opening brace ({) in a text string.</span></span>

<span data-ttu-id="75ca7-126">Расширения разметки отличаются от преобразователей типов.</span><span class="sxs-lookup"><span data-stu-id="75ca7-126">Markup extensions differ from type converters.</span></span> <span data-ttu-id="75ca7-127">Преобразователи типов обычно связаны с типами или членами.</span><span class="sxs-lookup"><span data-stu-id="75ca7-127">Type converters are typically associated with types or members.</span></span> <span data-ttu-id="75ca7-128">Они вызываются при создании графа объектов или при обнаружении текстового синтаксиса, связанного с этими сущностями, во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="75ca7-128">They are invoked when an object graph creation or a serialization encounters text syntax that is associated with those entities.</span></span>

<span data-ttu-id="75ca7-129">Расширения разметки связаны с отдельным вспомогательным классом службы, но могут применяться к любому значению члена.</span><span class="sxs-lookup"><span data-stu-id="75ca7-129">Markup extensions are associated with a single supporting service class, but can be applied for any member value.</span></span> <span data-ttu-id="75ca7-130">(Однако вы можете реализовать расширение разметки, чтобы намеренно ограничить его использование определенными членами или типами назначения, используя контекст службы.) Расширения разметки могут переопределить ассоциацию преобразователя типа.</span><span class="sxs-lookup"><span data-stu-id="75ca7-130">(However, you can implement your markup extension to deliberately restrict its use to certain members or destination types, by using service context.) Markup extensions can override a type converter association.</span></span> <span data-ttu-id="75ca7-131">Кроме того, их можно использовать, чтобы указать значение атрибута для членов, которые в противном случае не поддерживают текстовый синтаксис.</span><span class="sxs-lookup"><span data-stu-id="75ca7-131">Or you can use them to specify an attribute value for members that would not otherwise support a text syntax.</span></span>

<span data-ttu-id="75ca7-132">Дополнительные сведения о реализации шаблона расширения разметки для XAML см. в разделе [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75ca7-132">For more information about the markup extension implementation pattern for XAML, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="value-serializers"></a><span data-ttu-id="75ca7-133">Сериализаторы значений</span><span class="sxs-lookup"><span data-stu-id="75ca7-133">Value Serializers</span></span>

<span data-ttu-id="75ca7-134"><xref:System.Windows.Markup.ValueSerializer> — это специализированные преобразователь типов, оптимизированный для преобразования объекта в строку.</span><span class="sxs-lookup"><span data-stu-id="75ca7-134">A <xref:System.Windows.Markup.ValueSerializer> is a specialized type converter that is optimized for converting an object to a string.</span></span> <span data-ttu-id="75ca7-135">Объект <xref:System.Windows.Markup.ValueSerializer> для XAML не может реализовывать метод `ConvertFrom` .</span><span class="sxs-lookup"><span data-stu-id="75ca7-135">A <xref:System.Windows.Markup.ValueSerializer> for XAML might not implement the `ConvertFrom` method at all.</span></span> <span data-ttu-id="75ca7-136">Реализация <xref:System.Windows.Markup.ValueSerializer> получает службы так, будто это реализация <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="75ca7-136">A <xref:System.Windows.Markup.ValueSerializer> implementation obtains services in a manner that is like a <xref:System.ComponentModel.TypeConverter> implementation.</span></span> <span data-ttu-id="75ca7-137">Виртуальные методы предоставляют входной параметр `context` .</span><span class="sxs-lookup"><span data-stu-id="75ca7-137">The virtual methods provide an input `context` parameter.</span></span> <span data-ttu-id="75ca7-138">Параметр `context` имеет тип <xref:System.Windows.Markup.IValueSerializerContext>, который наследуется от интерфейса <xref:System.IServiceProvider> и содержит метод <xref:System.IServiceProvider.GetService%2A> .</span><span class="sxs-lookup"><span data-stu-id="75ca7-138">The `context` parameter is of type <xref:System.Windows.Markup.IValueSerializerContext>, which inherits from the <xref:System.IServiceProvider> interface and has a <xref:System.IServiceProvider.GetService%2A> method.</span></span>

<span data-ttu-id="75ca7-139">В системе типов XAML и реализациях средств записи XAML, которые используют циклическую обработку узлов XAML для сериализации,преобразователь значений, связанный с типом или членом, доступен по собственному свойству <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="75ca7-139">In the XAML type system and for XAML writer implementations that use XAML node loop processing for serialization, a value converter that is associated with a type or member is reported by its own <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="75ca7-140">Для средств записи XAML, выполняющих сериализацию, это значит, что если <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> и <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> существуют, преобразователь типов можно использовать для пути загрузки, а сериализатор значений — для пути сохранения.</span><span class="sxs-lookup"><span data-stu-id="75ca7-140">The meaning to XAML writers that perform serialization is that if a <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> and <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> exist, the type converter should be used for the load path and the value serializer should be used for the save path.</span></span> <span data-ttu-id="75ca7-141">Если <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> существует, но <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> — `null`, преобразователь типов также используется для пути сохранения.</span><span class="sxs-lookup"><span data-stu-id="75ca7-141">If <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> exists but <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> is `null`, the type converter is also used for the save path.</span></span>

## <a name="other-value-converters"></a><span data-ttu-id="75ca7-142">Другие преобразователи значений</span><span class="sxs-lookup"><span data-stu-id="75ca7-142">Other Value Converters</span></span>

<span data-ttu-id="75ca7-143">Преобразователь значений можно расширить за границы конкретных шаблонов преобразователя типов или расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="75ca7-143">A value converter is extensible beyond the specific patterns of a type converter or a markup extension.</span></span> <span data-ttu-id="75ca7-144">Однако эта настройка также потребует переосмысления системы типа XAML, как это предусмотрено службами .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="75ca7-144">However, this customization would also require the redefinition of the XAML type system as provided by .NET XAML Services.</span></span> <span data-ttu-id="75ca7-145">Существующая система типов XAML содержит представления и системы отчетности для преобразователей типов, расширений разметки и сериализаторов значений, но не для пользовательских форм преобразования значений.</span><span class="sxs-lookup"><span data-stu-id="75ca7-145">The existing XAML type system has representations and reporting systems for type converters, markup extensions, and value serializers, but not for custom forms of value conversion.</span></span> <span data-ttu-id="75ca7-146">Если вам требуется создать пользовательские преобразователи значений, используйте тип <xref:System.Xaml.Schema.XamlValueConverter%601> .</span><span class="sxs-lookup"><span data-stu-id="75ca7-146">If you want to create custom value converters, use the <xref:System.Xaml.Schema.XamlValueConverter%601> type.</span></span>

## <a name="type-converters-and-markup-extensions-in-combination"></a><span data-ttu-id="75ca7-147">Сочетание преобразователей типов и расширений разметки</span><span class="sxs-lookup"><span data-stu-id="75ca7-147">Type Converters and Markup Extensions in Combination</span></span>

<span data-ttu-id="75ca7-148">Расширения разметки и преобразователи типов используются в языке XAML в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="75ca7-148">Markup extensions and type converters are used for different situations in XAML.</span></span> <span data-ttu-id="75ca7-149">Хотя для расширения разметки контекст доступен, поведение преобразования типов свойств, когда расширение разметки предоставляет значение, обычно не включается в реализацию расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="75ca7-149">Although context is available for markup extension usages, type conversion behavior of properties where a markup extension provides a value is generally is not checked in the markup extension implementations.</span></span> <span data-ttu-id="75ca7-150">Другими словами, даже если расширение разметки возвращает текстовую строку в качестве выходных данных `ProvideValue` , преобразование типа для этой строки относительно конкретного свойства или типа значения свойства не применяется.</span><span class="sxs-lookup"><span data-stu-id="75ca7-150">In other words, even if a markup extension returns a text string as its `ProvideValue` output, type conversion behavior on that string as applied to a specific property or property value type is not invoked.</span></span> <span data-ttu-id="75ca7-151">Как правило, цель расширения разметки — обработать строку и вернуть объект без участия какого-либо преобразователя типов.</span><span class="sxs-lookup"><span data-stu-id="75ca7-151">Generally, the purpose of a markup extension is to process a string and return an object without any type converter involved.</span></span>

## <a name="service-context-for-a-value-converter"></a><span data-ttu-id="75ca7-152">Контекст службы для преобразователя значений</span><span class="sxs-lookup"><span data-stu-id="75ca7-152">Service Context for a Value Converter</span></span>

<span data-ttu-id="75ca7-153">При реализации преобразователя значений часто требуется доступ к контексту, в котором он применяется.</span><span class="sxs-lookup"><span data-stu-id="75ca7-153">When you implement a value converter, you often need access to a context in which the value converter is applied.</span></span> <span data-ttu-id="75ca7-154">Этот контекст называют контекстом службы.</span><span class="sxs-lookup"><span data-stu-id="75ca7-154">This context is known as the service context.</span></span> <span data-ttu-id="75ca7-155">Контекст службы может включать информацию, такую как активный контекст схемы XAML, доступ к системе отображения типов, которую предоставляют контекст схемы XAML и автор объектов XAML, и так далее.</span><span class="sxs-lookup"><span data-stu-id="75ca7-155">The service context might include information such as the active XAML schema context, access to the type-mapping system that the XAML schema context and XAML object writer provide, and so on.</span></span> <span data-ttu-id="75ca7-156">Дополнительные сведения о контекстах служб, доступных для преобразователя значений, и способах доступа к службам, которые могут предоставить контекст службы, см. в разделе [Service Contexts Available to Type Converters and Markup Extensions](service-contexts-with-type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="75ca7-156">For more information about the service contexts available for a value converter and how to access the services that a service context might provide, see [Service Contexts Available to Type Converters and Markup Extensions](service-contexts-with-type-converters-and-markup-extensions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75ca7-157">См. также</span><span class="sxs-lookup"><span data-stu-id="75ca7-157">See also</span></span>

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [<span data-ttu-id="75ca7-158">Общие сведения о расширениях разметки для XAML</span><span class="sxs-lookup"><span data-stu-id="75ca7-158">Markup Extensions for XAML Overview</span></span>](markup-extensions-overview.md)
- [<span data-ttu-id="75ca7-159">Общие сведения о преобразователях типов для XAML</span><span class="sxs-lookup"><span data-stu-id="75ca7-159">Type Converters for XAML Overview</span></span>](type-converters-overview.md)
- [<span data-ttu-id="75ca7-160">Служебные контексты, доступные для расширений разметки и преобразователей типов</span><span class="sxs-lookup"><span data-stu-id="75ca7-160">Service Contexts Available to Type Converters and Markup Extensions</span></span>](service-contexts-with-type-converters-and-markup-extensions.md)