---
title: Расширение разметки x:NULL
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: f4971d61d11ec14eaeac2d2f202353e4921b9325
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549448"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="ab06a-102">Расширение разметки x:NULL</span><span class="sxs-lookup"><span data-stu-id="ab06a-102">x:Null Markup Extension</span></span>

<span data-ttu-id="ab06a-103">Задает `null` в качестве значения для элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="ab06a-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="ab06a-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="ab06a-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="ab06a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab06a-105">Remarks</span></span>

<span data-ttu-id="ab06a-106">Ключевое слово для пустой ссылки в C# и C++ равно null.</span><span class="sxs-lookup"><span data-stu-id="ab06a-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="ab06a-107">Ключевое слово Microsoft Visual Basic для пустой ссылки — это `Nothing` , но всегда используется `{x:Null}` как использование XAML, независимо от того, какой язык кода программной части связан с XAML.</span><span class="sxs-lookup"><span data-stu-id="ab06a-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="ab06a-108">`x:Null`Расширение разметки не имеет устанавливаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="ab06a-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="ab06a-109">Использование значения NULL часто связано с выдержкой из XAML-элемента в <xref:System.Nullable%601> значении CLR.</span><span class="sxs-lookup"><span data-stu-id="ab06a-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="ab06a-110">`x:Null`Расширение разметки, как и все расширения разметки XAML, использует фигурные скобки ( `{,}` ) для экранирования обработки значений атрибутов, отличных от литералов или ссылок обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="ab06a-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="ab06a-111">Синтаксис атрибутов — это синтаксис, который чаще всего используется с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="ab06a-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="ab06a-112">Синтаксис объектного элемента `<x:Null />` технически возможен, но редко используется, так как `x:Null` расширение разметки не имеет параметров позиционирования или аргументов конструкции.</span><span class="sxs-lookup"><span data-stu-id="ab06a-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="ab06a-113">Дополнительные сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span><span class="sxs-lookup"><span data-stu-id="ab06a-113">For information about markup extensions, see [Markup Extensions and WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span></span>

<span data-ttu-id="ab06a-114">В службах .NET XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.NullExtension> классом.</span><span class="sxs-lookup"><span data-stu-id="ab06a-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="ab06a-115">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="ab06a-115">WPF Usage Notes</span></span>

<span data-ttu-id="ab06a-116">Обратите внимание, что `null` не обязательно является начальным значением свойства зависимости ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="ab06a-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="ab06a-117">Начальное значение по умолчанию может различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству.</span><span class="sxs-lookup"><span data-stu-id="ab06a-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="ab06a-118">Многие свойства зависимостей не принимаются `null` в качестве значения с помощью разметки или кода из-за реализаций обратного вызова проверки.</span><span class="sxs-lookup"><span data-stu-id="ab06a-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="ab06a-119">См. сведения о [свойствах зависимостей](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span><span class="sxs-lookup"><span data-stu-id="ab06a-119">For more information about dependency properties, see [Dependency Properties Overview](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab06a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ab06a-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="ab06a-121">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="ab06a-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="ab06a-122">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="ab06a-122">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
