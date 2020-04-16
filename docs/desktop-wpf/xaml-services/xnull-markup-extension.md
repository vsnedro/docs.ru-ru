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
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432698"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="7b274-102">Расширение разметки x:NULL</span><span class="sxs-lookup"><span data-stu-id="7b274-102">x:Null Markup Extension</span></span>

<span data-ttu-id="7b274-103">`null` Определяется как значение для участника XAML.</span><span class="sxs-lookup"><span data-stu-id="7b274-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="7b274-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="7b274-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="7b274-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b274-105">Remarks</span></span>

<span data-ttu-id="7b274-106">Ключевое слово для нулевой ссылки в СЗ и СЗ является нулевым.</span><span class="sxs-lookup"><span data-stu-id="7b274-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="7b274-107">Ключевое слово Microsoft Visual Basic `Nothing`для нулевой `{x:Null}` ссылки, но вы всегда используете в качестве использования XAML независимо от того, какой код за языком вы связываете с XAML.</span><span class="sxs-lookup"><span data-stu-id="7b274-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="7b274-108">Расширение `x:Null` разметки не имеет установленных свойств.</span><span class="sxs-lookup"><span data-stu-id="7b274-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="7b274-109">Использование нулевой часто связано с экспозицией члена <xref:System.Nullable%601> XAML значения CLR.</span><span class="sxs-lookup"><span data-stu-id="7b274-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="7b274-110">Расширение `x:Null` разметки, как и все расширения разметки`{,}`XAML, использует скобки () для избежания обработки значений атрибутов, чтобы быть иным, чем буквальные или события обработчик ссылки.</span><span class="sxs-lookup"><span data-stu-id="7b274-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="7b274-111">Синтаксис атрибутов является синтаксисом, наиболее часто используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="7b274-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="7b274-112">Синтаксис `<x:Null />` элемента объекта технически возможен, но `x:Null` редко используется, поскольку расширение разметки не имеет позиционных параметров или аргументов конструкции.</span><span class="sxs-lookup"><span data-stu-id="7b274-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="7b274-113">Для получения информации о расширениях разметки см. [Расширение разметки и WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7b274-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="7b274-114">В службах .NET XAML обработка этого расширения <xref:System.Windows.Markup.NullExtension> разметки определяется классом.</span><span class="sxs-lookup"><span data-stu-id="7b274-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="7b274-115">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="7b274-115">WPF Usage Notes</span></span>

<span data-ttu-id="7b274-116">Обратите `null` внимание, что это не обязательно начальное неустановленное значение для свойства зависимости эталонного типа.</span><span class="sxs-lookup"><span data-stu-id="7b274-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="7b274-117">Начальное значение по умолчанию может варьироваться для каждого свойства зависимости и может быть основано на метаданных, специфичных свойствах.</span><span class="sxs-lookup"><span data-stu-id="7b274-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="7b274-118">Многие свойства зависимости `null` не принимаются в качестве значения, либо через разметку, либо код из-за их реализации возврата проверки.</span><span class="sxs-lookup"><span data-stu-id="7b274-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="7b274-119">Для получения дополнительной информации [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md)о свойствах зависимостей см.</span><span class="sxs-lookup"><span data-stu-id="7b274-119">For more information about dependency properties, see [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b274-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7b274-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="7b274-121">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7b274-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="7b274-122">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="7b274-122">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
