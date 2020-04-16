---
title: Встроенный тип XAML x:XData
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432794"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="df4b4-102">Встроенный тип XAML x:XData</span><span class="sxs-lookup"><span data-stu-id="df4b4-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="df4b4-103">Позволяет разместить острова данных XML в рамках производства XAML.</span><span class="sxs-lookup"><span data-stu-id="df4b4-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="df4b4-104">XML элементы внутри `x:XData` не должны рассматриваться процессорами XAML, как если бы они являются частью действующего пространства имен XAML по умолчанию или любого другого пространства имен XAML.</span><span class="sxs-lookup"><span data-stu-id="df4b4-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="df4b4-105">`x:XData`может содержать произвольно хорошо сформированный XML.</span><span class="sxs-lookup"><span data-stu-id="df4b4-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="df4b4-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="df4b4-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="df4b4-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="df4b4-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="df4b4-108">Единый корневой элемент замкнутого острова данных.</span><span class="sxs-lookup"><span data-stu-id="df4b4-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="df4b4-109">Для большинства возможных потребителей XML, не имеющая ни одного корня, считается недействительным.</span><span class="sxs-lookup"><span data-stu-id="df4b4-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="df4b4-110">В частности, требуется единый корень, если `x:XData` он предназначен в качестве источника данных XML для WPF или многих других технологий, которые используют источники XML для связывания данных.</span><span class="sxs-lookup"><span data-stu-id="df4b4-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="df4b4-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="df4b4-111">Optional.</span></span> <span data-ttu-id="df4b4-112">XML, представляющий данные XML.</span><span class="sxs-lookup"><span data-stu-id="df4b4-112">XML that represents the XML data.</span></span> <span data-ttu-id="df4b4-113">Любое количество элементов может содержаться в качестве данных элементов и вложенных элементов, которые могут содержаться в других элементах; однако применяются общие правила XML.</span><span class="sxs-lookup"><span data-stu-id="df4b4-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="df4b4-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="df4b4-114">Remarks</span></span>

<span data-ttu-id="df4b4-115">Элементы XML `x:XData` внутри объекта могут повторно декларировать все возможные пространства имен и префиксы, содержащие XMLDOM в данных.</span><span class="sxs-lookup"><span data-stu-id="df4b4-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="df4b4-116">Программный доступ к данным `x:XData` XML и типу XAML возможен в службах <xref:System.Windows.Markup.XData> .NET XAML через класс.</span><span class="sxs-lookup"><span data-stu-id="df4b4-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="df4b4-117">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="df4b4-117">WPF Usage Notes</span></span>

<span data-ttu-id="df4b4-118">Объект `x:XData` в основном используется в качестве <xref:System.Windows.Data.XmlDataProvider>детского объекта объекта или же <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> в качестве объекта детского свойства (в XAML это обычно выражается в синтаксисе элемента свойства).</span><span class="sxs-lookup"><span data-stu-id="df4b4-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="df4b4-119">Данные должны обычно переопределять базовое пространство имен XML в пределах острова данных, чтобы быть новым пространством имен XML по умолчанию (установлено на пустую строку).</span><span class="sxs-lookup"><span data-stu-id="df4b4-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="df4b4-120">Это проще всего для островов простых данных, потому что <xref:System.Windows.Data.Binding.XPath%2A> выражения, которые используются для ссылки и привязки к данным, могут избежать включения префиксов.</span><span class="sxs-lookup"><span data-stu-id="df4b4-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="df4b4-121">Более сложные острова данных могут определить несколько префиксов для данных и использовать определенную префикс для пространства имен XML в корне.</span><span class="sxs-lookup"><span data-stu-id="df4b4-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="df4b4-122">В этом случае <xref:System.Windows.Data.Binding.XPath%2A> все ссылки на выражения должны включать соответствующую префикс с картой имен.</span><span class="sxs-lookup"><span data-stu-id="df4b4-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="df4b4-123">Для получения дополнительной информации [см.](../data/data-binding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="df4b4-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="df4b4-124">Технически, `x:XData` может быть использован в качестве содержания любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="df4b4-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="df4b4-125">Тем <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> не менее, является единственным заметным осуществления.</span><span class="sxs-lookup"><span data-stu-id="df4b4-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="df4b4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="df4b4-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="df4b4-127">Обзор связывания данных</span><span class="sxs-lookup"><span data-stu-id="df4b4-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="df4b4-128">Привязка расширения разметки</span><span class="sxs-lookup"><span data-stu-id="df4b4-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
