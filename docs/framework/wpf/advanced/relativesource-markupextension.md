---
title: Расширение разметки RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 6301299da966ade9b5cc7ccd105c8269a486744e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646231"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="ab1c7-102">Расширение разметки RelativeSource</span><span class="sxs-lookup"><span data-stu-id="ab1c7-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="ab1c7-103">Определяет свойства связывающего <xref:System.Windows.Data.RelativeSource> источника, который будет использоваться в [рамках расширения связывания разметки,](binding-markup-extension.md)или при настройке <xref:System.Windows.Data.Binding.RelativeSource%2A> свойства <xref:System.Windows.Data.Binding> элемента, установленного в XAML.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="ab1c7-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="ab1c7-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="ab1c7-105">Использование атрибута XAML (вложенный в расширение Binding)</span><span class="sxs-lookup"><span data-stu-id="ab1c7-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="ab1c7-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="ab1c7-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="ab1c7-107">-или-</span><span class="sxs-lookup"><span data-stu-id="ab1c7-107">-or-</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a><span data-ttu-id="ab1c7-108">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="ab1c7-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="ab1c7-109">Это может быть:</span><span class="sxs-lookup"><span data-stu-id="ab1c7-109">One of the following:</span></span><br /><br /> <span data-ttu-id="ab1c7-110">- Токен `Self`строки; соответствует как <xref:System.Windows.Data.RelativeSource> созданный с <xref:System.Windows.Data.RelativeSource.Mode%2A> его <xref:System.Windows.Data.RelativeSourceMode.Self>свойством установлен на .</span><span class="sxs-lookup"><span data-stu-id="ab1c7-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="ab1c7-111">- Токен `TemplatedParent`строки; соответствует как <xref:System.Windows.Data.RelativeSource> созданный с <xref:System.Windows.Data.RelativeSource.Mode%2A> его <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>свойством установлен на .</span><span class="sxs-lookup"><span data-stu-id="ab1c7-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="ab1c7-112">- Токен `PreviousData`строки; соответствует как <xref:System.Windows.Data.RelativeSource> созданный с <xref:System.Windows.Data.RelativeSource.Mode%2A> его <xref:System.Windows.Data.RelativeSourceMode.PreviousData>свойством установлен на .</span><span class="sxs-lookup"><span data-stu-id="ab1c7-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="ab1c7-113">- Смотрите ниже `FindAncestor` для получения информации о режиме.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="ab1c7-114">Строковая лексема `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="ab1c7-115">Использовании этой лексемы осуществляет переход в режим, где `RelativeSource` задает тип предка и (при необходимости) уровень предка.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="ab1c7-116">Это соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="ab1c7-117">Требуется для режима `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="ab1c7-118">Имя типа, которое заполняет свойство <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="ab1c7-119">Необязательно для режима `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="ab1c7-120">Уровень предка (вычисляется в направлении родителя в логическом дереве).</span><span class="sxs-lookup"><span data-stu-id="ab1c7-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="ab1c7-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab1c7-121">Remarks</span></span>

<span data-ttu-id="ab1c7-122">`{RelativeSource TemplatedParent}`обязательные обычаи являются ключевым методом, который учитывает более широкую концепцию разделения uI элемента управления и логику элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="ab1c7-123">Это делает возможным привязку из определения шаблона к созданному по шаблону родительскому элементу (экземпляр объекта времени выполнения, в котором применяется шаблон).</span><span class="sxs-lookup"><span data-stu-id="ab1c7-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="ab1c7-124">В этом случае [расширение шаблонной разметки](templatebinding-markup-extension.md) на самом деле `{Binding RelativeSource={RelativeSource TemplatedParent}}`является сокращением для следующего связывающего выражения: .</span><span class="sxs-lookup"><span data-stu-id="ab1c7-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="ab1c7-125">`TemplateBinding`или `{RelativeSource TemplatedParent}` обычаи имеют отношение только в XAML, который определяет шаблон.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="ab1c7-126">Для получения дополнительной [TemplateBinding Markup Extension](templatebinding-markup-extension.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="ab1c7-127">`{RelativeSource FindAncestor}`в основном используется в шаблонах управления или предсказуемых автономных композициях uI, в тех случаях, когда контроль всегда должен находиться в визуальном древе определенного типа предка.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="ab1c7-128">Например, элементы в элементе управления элементами могут использовать вхождения `FindAncestor` для привязки к свойствам предка элемента управления элементами.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="ab1c7-129">Либо элементы, которые являются частью композиции элемента управления в шаблоне, могут использовать привязки `FindAncestor` к родительским элементам в той же структуре композиции.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="ab1c7-130">В синтаксисе объектного элемента для режима `FindAncestor`, показанного выше в разделах синтаксиса XAML, второй синтаксис объектного элемента используется специально для режима `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="ab1c7-131">Режим `FindAncestor` требует значения <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="ab1c7-132">Необходимо установить <xref:System.Windows.Data.RelativeSource.AncestorType%2A> в качестве атрибута ссылку на расширение [x:Type Markup](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) к типу предка для поиска.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="ab1c7-133">Значение <xref:System.Windows.Data.RelativeSource.AncestorType%2A> используется при обработке запроса привязки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="ab1c7-134">Для режима `FindAncestor` необязательное свойство <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> может помочь устранить неоднозначность поиска предка в случаях, где в дереве элементов, возможно, существует более одного предка данного типа.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="ab1c7-135">Дополнительные сведения об использовании режима `FindAncestor` см. в разделе <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="ab1c7-136">`{RelativeSource Self}`полезен для сценариев, где одно свойство экземпляра должно зависеть от значения другого свойства того же экземпляра, и между этими двумя свойствами уже не существует общих отношений собственности зависимости (например, принуждения).</span><span class="sxs-lookup"><span data-stu-id="ab1c7-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="ab1c7-137">Хотя на объекте редко существуют два свойства, такие, что значения буквально идентичны (и одинаково `Converter` набраны), `{RelativeSource Self}`можно также применить параметр к связке, которая имеет, и использовать преобразователь для преобразования между исходными и целевыми типами.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="ab1c7-138">Другой сценарий для `{RelativeSource Self}` является <xref:System.Windows.MultiDataTrigger>частью .</span><span class="sxs-lookup"><span data-stu-id="ab1c7-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="ab1c7-139">Например, следующий код XAML определяет такой элемент <xref:System.Windows.Shapes.Rectangle>, что независимо от того, какое значение вводится для свойства <xref:System.Windows.FrameworkElement.Width%2A>, объектом <xref:System.Windows.Shapes.Rectangle> всегда является квадрат: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="ab1c7-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="ab1c7-140">`{RelativeSource PreviousData}`полезен либо в шаблонах данных, либо в тех случаях, когда привязки используют сбор в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="ab1c7-141">Можно выделить `{RelativeSource PreviousData}` взаимосвязь между смежными элементами данных в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="ab1c7-142">Соответствующей методикой является установление привязки <xref:System.Windows.Data.MultiBinding> между текущим и предыдущим элементами в источнике данных и использование преобразователя в этой привязке для определения различия между двумя элементами и их свойствами.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="ab1c7-143">В следующем примере первый элемент <xref:System.Windows.Controls.TextBlock> в шаблоне элементов отображает текущий номер.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="ab1c7-144">Второй <xref:System.Windows.Controls.TextBlock> привязкой <xref:System.Windows.Data.MultiBinding> является то, <xref:System.Windows.Data.Binding> что номинально имеет два компонента: текущая запись, и `{RelativeSource PreviousData}`связывание, которое намеренно использует предыдущую запись данных с помощью .</span><span class="sxs-lookup"><span data-stu-id="ab1c7-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="ab1c7-145">Затем преобразователь в объекте <xref:System.Windows.Data.MultiBinding> вычисляет разницу и возвращает ее в привязку.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
```

<span data-ttu-id="ab1c7-146">Описание связывания данных как концепции здесь не рассматривается, [см.](../../../desktop-wpf/data/data-binding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ab1c7-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="ab1c7-147">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML обработка этого расширения <xref:System.Windows.Data.RelativeSource> разметки определяется классом.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="ab1c7-148">`RelativeSource` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="ab1c7-149">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="ab1c7-150">Все расширения разметки в `{` XAML используют и `}` символы в их синтаксисе атрибута, который является конвенцией, с помощью которой процессор XAML признает, что расширение разметки должно обрабатывать атрибут.</span><span class="sxs-lookup"><span data-stu-id="ab1c7-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="ab1c7-151">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ab1c7-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab1c7-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ab1c7-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="ab1c7-153">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="ab1c7-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ab1c7-154">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="ab1c7-154">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="ab1c7-155">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="ab1c7-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="ab1c7-156">Обзор связывания данных</span><span class="sxs-lookup"><span data-stu-id="ab1c7-156">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ab1c7-157">Общие сведения об объявлении привязок</span><span class="sxs-lookup"><span data-stu-id="ab1c7-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="ab1c7-158">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="ab1c7-158">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
